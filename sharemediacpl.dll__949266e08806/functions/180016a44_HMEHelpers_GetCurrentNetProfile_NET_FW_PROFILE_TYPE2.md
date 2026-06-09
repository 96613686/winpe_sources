# HMEHelpers::GetCurrentNetProfile(NET_FW_PROFILE_TYPE2_ *)

- ea: `0x180016a44`
- end: `0x180016af7`
- name: `?GetCurrentNetProfile@HMEHelpers@@YAJPEAW4NET_FW_PROFILE_TYPE2_@@@Z`
- size: `179`
- prototype: `__int64 __fastcall(HMEHelpers *__hidden this, enum NET_FW_PROFILE_TYPE2_ *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c3d0`

## callees

- `0x180016a44`
- `0x18001e010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180016a87`
- `ole32!CoCreateInstance` at `0x180016a87`

## pseudocode

```c
__int64 __fastcall HMEHelpers::GetCurrentNetProfile(HMEHelpers *this, enum NET_FW_PROFILE_TYPE2_ *a2)
{
  HRESULT v3; // edi
  bool v4; // zf
  int v6; // [rsp+40h] [rbp+8h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  if ( this )
  {
    ppv = 0;
    v3 = CoCreateInstance(
           &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
           0,
           1u,
           &GUID_98325047_c671_4174_8d81_defcd3f03186,
           &ppv);
    if ( v3 >= 0 )
    {
      v6 = 0;
      v3 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 56LL))(ppv, &v6);
      if ( v3 >= 0 )
      {
        v4 = (v6 & 1) == 0;
        *(_DWORD *)this = 4;
        if ( v4 )
        {
          if ( (v6 & 2) != 0 )
            *(_DWORD *)this = 2;
        }
        else
        {
          *(_DWORD *)this = 1;
        }
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016a44  mov     [rsp+arg_10], rbx
0x180016a49  push    rdi
0x180016a4a  sub     rsp, 30h
0x180016a4e  mov     rbx, rcx
0x180016a51  test    rcx, rcx
0x180016a54  jnz     short loc_180016A60
0x180016a56  mov     edi, 80004003h
0x180016a5b  jmp     loc_180016AEA
0x180016a60  xor     edx, edx; pUnkOuter
0x180016a62  mov     [rsp+38h+arg_8], 0
0x180016a6b  lea     rax, [rsp+38h+arg_8]
0x180016a70  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180016a77  mov     [rsp+38h+ppv], rax; ppv
0x180016a7c  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x180016a83  lea     r8d, [rdx+1]; dwClsContext
0x180016a87  call    cs:__imp_CoCreateInstance
0x180016a8d  mov     edi, eax
0x180016a8f  test    eax, eax
0x180016a91  js      short loc_180016AEA
0x180016a93  mov     rcx, [rsp+38h+arg_8]
0x180016a98  lea     rdx, [rsp+38h+arg_0]
0x180016a9d  mov     [rsp+38h+arg_0], 0
0x180016aa5  mov     rax, [rcx]
0x180016aa8  mov     rax, [rax+38h]
0x180016aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ab1  mov     edi, eax
0x180016ab3  test    eax, eax
0x180016ab5  js      short loc_180016AD9
0x180016ab7  test    byte ptr [rsp+38h+arg_0], 1
0x180016abc  mov     dword ptr [rbx], 4
0x180016ac2  jz      short loc_180016ACC
0x180016ac4  mov     dword ptr [rbx], 1
0x180016aca  jmp     short loc_180016AD9
0x180016acc  test    byte ptr [rsp+38h+arg_0], 2
0x180016ad1  jz      short loc_180016AD9
0x180016ad3  mov     dword ptr [rbx], 2
0x180016ad9  mov     rcx, [rsp+38h+arg_8]
0x180016ade  mov     rax, [rcx]
0x180016ae1  mov     rax, [rax+10h]
0x180016ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aea  mov     rbx, [rsp+38h+arg_10]
0x180016aef  mov     eax, edi
0x180016af1  add     rsp, 30h
0x180016af5  pop     rdi
0x180016af6  retn
```
