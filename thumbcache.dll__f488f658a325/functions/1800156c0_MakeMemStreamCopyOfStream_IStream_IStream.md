# MakeMemStreamCopyOfStream(IStream *,IStream * *)

- ea: `0x1800156c0`
- end: `0x180015790`
- name: `?MakeMemStreamCopyOfStream@@YAJPEAUIStream@@PEAPEAU1@@Z`
- size: `208`
- prototype: `__int64 __fastcall(struct IStream *pstmFrom, struct IStream **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180015390`
- `0x1800249d0`

## callees

- `0x1800156c0`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180015736`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Reset` at `0x180015736`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800156f7`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Size` at `0x1800156f7`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18001570e`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18001570e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x180015727`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Copy` at `0x180015727`

## pseudocode

```c
__int64 __fastcall MakeMemStreamCopyOfStream(struct IStream *pstmFrom, struct IStream **a2)
{
  HRESULT v4; // ebx
  IStream *v5; // rax
  IStream *v6; // rdi
  ULARGE_INTEGER pui; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  pui.QuadPart = 0;
  v4 = IStream_Size(pstmFrom, &pui);
  if ( v4 >= 0 )
  {
    if ( pui.HighPart )
    {
      return (unsigned int)-2147024673;
    }
    else
    {
      v5 = SHCreateMemStream(0, 0);
      v6 = v5;
      if ( v5 )
      {
        v4 = IStream_Copy(pstmFrom, v5, pui.LowPart);
        if ( v4 >= 0 )
        {
          IStream_Reset(v6);
          v4 = (**(__int64 (__fastcall ***)(IStream *, GUID *, struct IStream **))v6)(
                 v6,
                 &GUID_0000000c_0000_0000_c000_000000000046,
                 a2);
        }
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v6 + 16LL))(v6);
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800156c0  mov     [rsp+arg_10], rbx
0x1800156c5  push    rsi
0x1800156c6  push    rdi
0x1800156c7  push    r14
0x1800156c9  sub     rsp, 30h
0x1800156cd  mov     rax, cs:__security_cookie
0x1800156d4  xor     rax, rsp
0x1800156d7  mov     [rsp+48h+var_20], rax
0x1800156dc  mov     r14, rdx
0x1800156df  mov     qword ptr [rdx], 0
0x1800156e6  lea     rdx, [rsp+48h+pui]; pui
0x1800156eb  mov     qword ptr [rsp+48h+pui], 0
0x1800156f4  mov     rsi, rcx
0x1800156f7  call    cs:__imp_IStream_Size
0x1800156fd  mov     ebx, eax
0x1800156ff  test    eax, eax
0x180015701  js      short loc_180015765
0x180015703  cmp     dword ptr [rsp+48h+pui+4], 0
0x180015708  jnz     short loc_180015789
0x18001570a  xor     edx, edx; cbInit
0x18001570c  xor     ecx, ecx; pInit
0x18001570e  call    cs:__imp_SHCreateMemStream
0x180015714  mov     rdi, rax
0x180015717  test    rax, rax
0x18001571a  jz      short loc_180015782
0x18001571c  mov     r8d, dword ptr [rsp+48h+pui]; cb
0x180015721  mov     rdx, rax; pstmTo
0x180015724  mov     rcx, rsi; pstmFrom
0x180015727  call    cs:__imp_IStream_Copy
0x18001572d  mov     ebx, eax
0x18001572f  test    eax, eax
0x180015731  js      short loc_180015756
0x180015733  mov     rcx, rdi; pstm
0x180015736  call    cs:__imp_IStream_Reset
0x18001573c  mov     rcx, [rdi]
0x18001573f  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180015746  mov     r8, r14
0x180015749  mov     rax, [rcx]
0x18001574c  mov     rcx, rdi
0x18001574f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015754  mov     ebx, eax
0x180015756  mov     rax, [rdi]
0x180015759  mov     rcx, rdi
0x18001575c  mov     rax, [rax+10h]
0x180015760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015765  mov     eax, ebx
0x180015767  mov     rcx, [rsp+48h+var_20]
0x18001576c  xor     rcx, rsp; StackCookie
0x18001576f  call    __security_check_cookie
0x180015774  mov     rbx, [rsp+48h+arg_10]
0x180015779  add     rsp, 30h
0x18001577d  pop     r14
0x18001577f  pop     rdi
0x180015780  pop     rsi
0x180015781  retn
0x180015782  mov     ebx, 8007000Eh
0x180015787  jmp     short loc_180015765
0x180015789  mov     ebx, 800700DFh
0x18001578e  jmp     short loc_180015765
```
