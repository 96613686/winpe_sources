# NtlCoCreateInstanceAsNetConfigOpOrAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)

- ea: `0x180014ef8`
- end: `0x180014f4b`
- name: `?NtlCoCreateInstanceAsNetConfigOpOrAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z`
- size: `83`
- prototype: `__int64 __fastcall(HWND, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800150bc`
- `0x1800222dc`
- `0x18002a410`
- `0x18002c1d0`

## callees

- `0x1800149e8`
- `0x180014ae0`
- `0x180014be8`
- `0x180014ef8`

## pseudocode

```c
int __fastcall NtlCoCreateInstanceAsNetConfigOpOrAdmin(HWND a1, struct _GUID *a2, const struct _GUID *a3, void **a4)
{
  int result; // eax
  const struct _GUID *v7; // rdx
  const unsigned __int16 *v8; // r8
  const struct _GUID *v9; // r9
  int v10; // [rsp+50h] [rbp+18h] BYREF
  int v11; // [rsp+54h] [rbp+1Ch]

  v11 = HIDWORD(a3);
  v10 = 0;
  result = IsUserMemberOfNCO(&v10, (int *)a2);
  if ( result >= 0 )
  {
    if ( v10 )
      return CoCreateInstanceElevated(a1, v7, v8, v9, a4);
    else
      return CoCreateInstanceAsAdmin(a1, v7, (const struct _GUID *)v8, a4);
  }
  return result;
}

```

## disassembly

```asm
0x180014ef8  mov     rax, rsp
0x180014efb  mov     [rax+8], rbx
0x180014eff  mov     [rax+18h], r8
0x180014f03  push    rdi
0x180014f04  sub     rsp, 30h
0x180014f08  mov     rdi, rcx
0x180014f0b  mov     dword ptr [rax+18h], 0
0x180014f12  lea     rcx, [rax+18h]; int *
0x180014f16  mov     rbx, r9
0x180014f19  call    ?IsUserMemberOfNCO@@YAJPEAH0@Z; IsUserMemberOfNCO(int *,int *)
0x180014f1e  test    eax, eax
0x180014f20  js      short loc_180014F40
0x180014f22  cmp     [rsp+38h+arg_10], 0
0x180014f27  mov     rcx, rdi; HWND
0x180014f2a  jz      short loc_180014F38
0x180014f2c  mov     [rsp+38h+ppv], rbx; ppv
0x180014f31  call    ?CoCreateInstanceElevated@@YAJPEAUHWND__@@AEBU_GUID@@PEBG1PEAPEAX@Z; CoCreateInstanceElevated(HWND__ *,_GUID const &,ushort const *,_GUID const &,void * *)
0x180014f36  jmp     short loc_180014F40
0x180014f38  mov     r9, rbx; void **
0x180014f3b  call    ?CoCreateInstanceAsAdmin@@YAJPEAUHWND__@@AEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceAsAdmin(HWND__ *,_GUID const &,_GUID const &,void * *)
0x180014f40  mov     rbx, [rsp+38h+arg_0]
0x180014f45  add     rsp, 30h
0x180014f49  pop     rdi
0x180014f4a  retn
```
