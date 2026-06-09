# CanonicalizeUriPath(char const *,ulong,STRU *)

- ea: `0x18001c33c`
- end: `0x18001c3c2`
- name: `?CanonicalizeUriPath@@YAJPEBDKPEAVSTRU@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(char *, unsigned int, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180006ec8`
- `0x18000a9c4`

## callees

- `0x18001c33c`

## import_xrefs

- `iisutil!UlCleanAndCopyUrl` at `0x18001c38f`
- `iisutil!UlCleanAndCopyUrl` at `0x18001c38f`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001c39e`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18001c39e`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18001c36b`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18001c36b`

## pseudocode

```c
__int64 __fastcall CanonicalizeUriPath(char *a1, unsigned int a2, unsigned __int16 **a3)
{
  int v6; // ebx
  unsigned int v8; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int16 *v9; // [rsp+68h] [rbp+20h] BYREF

  v8 = 0;
  v9 = 0;
  v6 = STRU::Resize((STRU *)a3, 2 * a2 + 2);
  if ( v6 >= 0 )
  {
    v6 = UlCleanAndCopyUrl(a1, a2, &v8, a3[4], &v9);
    if ( v6 >= 0 )
    {
      STRU::SyncWithBuffer((STRU *)a3);
      if ( v9 )
        *v9 = 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001c33c  mov     [rsp+arg_0], rbx
0x18001c341  push    rbp
0x18001c342  push    rsi
0x18001c343  push    rdi
0x18001c344  sub     rsp, 30h
0x18001c348  mov     esi, edx
0x18001c34a  mov     [rsp+48h+arg_8], 0
0x18001c352  mov     rbp, rcx
0x18001c355  mov     [rsp+48h+arg_18], 0
0x18001c35e  lea     edx, ds:2[rdx*2]
0x18001c365  mov     rcx, r8
0x18001c368  mov     rdi, r8
0x18001c36b  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18001c371  mov     ebx, eax
0x18001c373  test    eax, eax
0x18001c375  js      short loc_18001C3B3
0x18001c377  mov     r9, [rdi+20h]
0x18001c37b  lea     rax, [rsp+48h+arg_18]
0x18001c380  lea     r8, [rsp+48h+arg_8]
0x18001c385  mov     [rsp+48h+var_28], rax
0x18001c38a  mov     edx, esi
0x18001c38c  mov     rcx, rbp
0x18001c38f  call    cs:__imp_?UlCleanAndCopyUrl@@YAJPEADKPEAKPEAGPEAPEAG@Z; UlCleanAndCopyUrl(char *,ulong,ulong *,ushort *,ushort * *)
0x18001c395  mov     ebx, eax
0x18001c397  test    eax, eax
0x18001c399  js      short loc_18001C3B3
0x18001c39b  mov     rcx, rdi
0x18001c39e  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18001c3a4  mov     rcx, [rsp+48h+arg_18]
0x18001c3a9  test    rcx, rcx
0x18001c3ac  jz      short loc_18001C3B3
0x18001c3ae  xor     eax, eax
0x18001c3b0  mov     [rcx], ax
0x18001c3b3  mov     eax, ebx
0x18001c3b5  mov     rbx, [rsp+48h+arg_0]
0x18001c3ba  add     rsp, 30h
0x18001c3be  pop     rdi
0x18001c3bf  pop     rsi
0x18001c3c0  pop     rbp
0x18001c3c1  retn
```
