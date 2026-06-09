# UlAtqReadFragmentFromCache(ushort const *,uchar *,ulong,ulong *)

- ea: `0x180015820`
- end: `0x1800158b7`
- name: `?UlAtqReadFragmentFromCache@@YAJPEBGPEAEKPEAK@Z`
- size: `151`
- prototype: `__int64 __fastcall(PCWSTR UrlPrefix, PVOID Buffer, ULONG BufferLength, PULONG BytesRead)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012050`
- `0x180015820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015899`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180015899`
- `HTTPAPI!HttpReadFragmentFromCache` at `0x180015885`
- `HTTPAPI!HttpReadFragmentFromCache` at `0x180015885`

## pseudocode

```c
__int64 __fastcall UlAtqReadFragmentFromCache(PCWSTR UrlPrefix, PVOID Buffer, ULONG BufferLength, PULONG BytesRead)
{
  void *v9; // rax
  signed int FragmentFromCache; // ebx
  PSRWLOCK SRWLock; // [rsp+40h] [rbp-38h] BYREF

  SRWLock = 0;
  if ( !g_pwpContext )
    return 2147942450LL;
  v9 = UL_APP_POOL::QueryAndLockHandle((WP_CONTEXT *)((char *)g_pwpContext + 760), &SRWLock);
  if ( v9 )
    FragmentFromCache = HttpReadFragmentFromCache(v9, UrlPrefix, 0, Buffer, BufferLength, BytesRead, 0);
  else
    FragmentFromCache = 6;
  ReleaseSRWLockShared(SRWLock);
  if ( FragmentFromCache > 0 )
    return (unsigned __int16)FragmentFromCache | 0x80070000;
  return (unsigned int)FragmentFromCache;
}

```

## disassembly

```asm
0x180015820  push    rbx
0x180015822  push    rbp
0x180015823  push    rsi
0x180015824  push    rdi
0x180015825  sub     rsp, 58h
0x180015829  mov     rbp, rcx
0x18001582c  mov     [rsp+78h+SRWLock], 0
0x180015835  mov     rcx, cs:?g_pwpContext@@3PEAVWP_CONTEXT@@EA; WP_CONTEXT * g_pwpContext
0x18001583c  mov     rbx, r9
0x18001583f  mov     edi, r8d
0x180015842  mov     rsi, rdx
0x180015845  test    rcx, rcx
0x180015848  jnz     short loc_180015851
0x18001584a  mov     eax, 80070032h
0x18001584f  jmp     short loc_1800158AE
0x180015851  add     rcx, 2F8h; this
0x180015858  lea     rdx, [rsp+78h+SRWLock]; void **
0x18001585d  call    ?QueryAndLockHandle@UL_APP_POOL@@QEAAPEAXPEAPEAX@Z; UL_APP_POOL::QueryAndLockHandle(void * *)
0x180015862  test    rax, rax
0x180015865  jz      short loc_18001588F
0x180015867  mov     [rsp+78h+Overlapped], 0; Overlapped
0x180015870  mov     r9, rsi; Buffer
0x180015873  mov     [rsp+78h+BytesRead], rbx; BytesRead
0x180015878  xor     r8d, r8d; ByteRange
0x18001587b  mov     rdx, rbp; UrlPrefix
0x18001587e  mov     [rsp+78h+BufferLength], edi; BufferLength
0x180015882  mov     rcx, rax; RequestQueueHandle
0x180015885  call    cs:__imp_HttpReadFragmentFromCache
0x18001588b  mov     ebx, eax
0x18001588d  jmp     short loc_180015894
0x18001588f  mov     ebx, 6
0x180015894  mov     rcx, [rsp+78h+SRWLock]; SRWLock
0x180015899  call    cs:__imp_ReleaseSRWLockShared
0x18001589f  test    ebx, ebx
0x1800158a1  jle     short loc_1800158AC
0x1800158a3  movzx   ebx, bx
0x1800158a6  or      ebx, 80070000h
0x1800158ac  mov     eax, ebx
0x1800158ae  add     rsp, 58h
0x1800158b2  pop     rdi
0x1800158b3  pop     rsi
0x1800158b4  pop     rbp
0x1800158b5  pop     rbx
0x1800158b6  retn
```
