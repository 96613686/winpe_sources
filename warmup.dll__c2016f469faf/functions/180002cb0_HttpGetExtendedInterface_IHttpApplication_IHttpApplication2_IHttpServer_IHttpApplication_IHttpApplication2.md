# HttpGetExtendedInterface<IHttpApplication,IHttpApplication2>(IHttpServer *,IHttpApplication *,IHttpApplication2 * *)

- ea: `0x180002cb0`
- end: `0x180002d18`
- name: `??$HttpGetExtendedInterface@VIHttpApplication@@VIHttpApplication2@@@@YAJPEAVIHttpServer@@PEAVIHttpApplication@@PEAPEAVIHttpApplication2@@@Z`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003398`
- `0x180003578`

## callees

- `0x180002cb0`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall HttpGetExtendedInterface<IHttpApplication,IHttpApplication2>(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  __int64 result; // rax
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v3 = *a1;
  v7 = 0;
  result = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v3 + 200))(a1, 0, &v7);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(__int64, GUID *, __int64, GUID *, __int64))(*(_QWORD *)v7 + 224LL))(
             v7,
             &GUID_3f75d9e6_1075_422c_ad89_93a85f2d7bdc,
             a2,
             &GUID_311a3b7a_b673_4a1c_8349_2e98a23cadcb,
             a3);
  return result;
}

```

## disassembly

```asm
0x180002cb0  mov     [rsp+arg_8], rbx
0x180002cb5  push    rdi
0x180002cb6  sub     rsp, 30h
0x180002cba  mov     rax, [rcx]
0x180002cbd  mov     rbx, r8
0x180002cc0  mov     rdi, rdx
0x180002cc3  mov     [rsp+38h+arg_0], 0
0x180002ccc  lea     r8, [rsp+38h+arg_0]
0x180002cd1  xor     edx, edx
0x180002cd3  mov     rax, [rax+0C8h]
0x180002cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cdf  test    eax, eax
0x180002ce1  js      short loc_180002D0D
0x180002ce3  mov     rcx, [rsp+38h+arg_0]
0x180002ce8  lea     r9, _GUID_311a3b7a_b673_4a1c_8349_2e98a23cadcb
0x180002cef  mov     r8, rdi
0x180002cf2  mov     [rsp+38h+var_18], rbx
0x180002cf7  lea     rdx, _GUID_3f75d9e6_1075_422c_ad89_93a85f2d7bdc
0x180002cfe  mov     rax, [rcx]
0x180002d01  mov     rax, [rax+0E0h]
0x180002d08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d0d  mov     rbx, [rsp+38h+arg_8]
0x180002d12  add     rsp, 30h
0x180002d16  pop     rdi
0x180002d17  retn
```
