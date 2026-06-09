# CSFPIntegrityCheckAndRepair::SFPCheckFile(__MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *,ushort *,int,ushort *,int *,__MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *,ISFPRebootCallback *,ISFPProgressCallback *)

- ea: `0x180006660`
- end: `0x1800067a6`
- name: `?SFPCheckFile@CSFPIntegrityCheckAndRepair@@UEAAJPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0001@@PEAGH1PEAHPEAU__MIDL___MIDL_itf_wrpintapi_0000_0000_0002@@PEAUISFPRebootCallback@@PEAUISFPProgressCallback@@@Z`
- size: `326`
- prototype: `__int64 __fastcall(CSFPIntegrityCheckAndRepair *this, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *, unsigned __int16 *, int, unsigned __int16 *, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, struct ISFPRebootCallback *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180006660`
- `0x18001b7b0`
- `0x18001c010`

## import_xrefs

- `setupapi!PnpIsFilePnpDriver` at `0x1800066e5`
- `setupapi!PnpIsFilePnpDriver` at `0x1800066e5`

## pseudocode

```c
__int64 __fastcall CSFPIntegrityCheckAndRepair::SFPCheckFile(
        CSFPIntegrityCheckAndRepair *this,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int16 *a5,
        int *a6,
        struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *a7,
        struct ISFPRebootCallback *a8)
{
  __int64 result; // rax
  int v13; // [rsp+60h] [rbp-58h] BYREF
  int v14; // [rsp+64h] [rbp-54h] BYREF

  v14 = 0;
  v13 = 1;
  if ( !a7 || !a6 )
    return 2147942487LL;
  *(_QWORD *)a7 = 0;
  *((_QWORD *)a7 + 1) = 0;
  *((_DWORD *)a7 + 4) = 0;
  *a6 = 0;
  if ( a2 || (unsigned int)PnpIsFilePnpDriver(a3, &v14) )
  {
    result = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0001 *, __int64, unsigned __int16 *, int, unsigned __int16 *, struct ISFPRebootCallback *, _QWORD, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, int *))(*(_QWORD *)this + 80LL))(
               this,
               a2,
               1,
               a3,
               a4,
               a5,
               a8,
               0,
               a6,
               a7,
               &v13);
  }
  else
  {
    if ( v14 != 1 )
      return 2147942450LL;
    result = (*(__int64 (__fastcall **)(CSFPIntegrityCheckAndRepair *, _QWORD, __int64, unsigned __int16 *, int, _QWORD, _QWORD, _QWORD, int *, struct __MIDL___MIDL_itf_wrpintapi_0000_0000_0002 *, int *))(*(_QWORD *)this + 80LL))(
               this,
               0,
               2,
               a3,
               a4,
               0,
               0,
               0,
               a6,
               a7,
               &v13);
  }
  if ( (int)result >= 0 && v13 == 2 )
    return 2147956481LL;
  return result;
}

```

## disassembly

```asm
0x180006660  push    rbx
0x180006662  push    rbp
0x180006663  push    rsi
0x180006664  push    rdi
0x180006665  push    r12
0x180006667  push    r13
0x180006669  push    r14
0x18000666b  push    r15
0x18000666d  sub     rsp, 78h
0x180006671  mov     rax, cs:__security_cookie
0x180006678  xor     rax, rsp
0x18000667b  mov     [rsp+0B8h+var_50], rax
0x180006680  mov     rbx, [rsp+0B8h+arg_30]
0x180006688  mov     rbp, rdx
0x18000668b  mov     r12, [rsp+0B8h+arg_20]
0x180006693  xor     edx, edx
0x180006695  mov     rdi, [rsp+0B8h+arg_28]
0x18000669d  mov     r15d, r9d
0x1800066a0  mov     r13, [rsp+0B8h+arg_38]
0x1800066a8  mov     rsi, r8
0x1800066ab  mov     [rsp+0B8h+var_54], edx
0x1800066af  mov     r14, rcx
0x1800066b2  mov     [rsp+0B8h+var_58], 1
0x1800066ba  test    rbx, rbx
0x1800066bd  jz      loc_180006783
0x1800066c3  test    rdi, rdi
0x1800066c6  jz      loc_180006783
0x1800066cc  mov     [rbx], rdx
0x1800066cf  mov     [rbx+8], rdx
0x1800066d3  mov     [rbx+10h], edx
0x1800066d6  mov     [rdi], edx
0x1800066d8  test    rbp, rbp
0x1800066db  jnz     short loc_18000672D
0x1800066dd  lea     rdx, [rsp+0B8h+var_54]
0x1800066e2  mov     rcx, r8
0x1800066e5  call    cs:__imp_PnpIsFilePnpDriver
0x1800066eb  xor     edx, edx
0x1800066ed  test    eax, eax
0x1800066ef  jnz     short loc_18000672D
0x1800066f1  cmp     [rsp+0B8h+var_54], 1
0x1800066f6  jz      short loc_180006702
0x1800066f8  mov     eax, 80070032h
0x1800066fd  jmp     loc_180006788
0x180006702  lea     rcx, [rsp+0B8h+var_58]
0x180006707  mov     r8d, 2
0x18000670d  mov     [rsp+0B8h+var_68], rcx
0x180006712  mov     [rsp+0B8h+var_70], rbx
0x180006717  mov     [rsp+0B8h+var_78], rdi
0x18000671c  mov     [rsp+0B8h+var_80], rdx
0x180006721  mov     [rsp+0B8h+var_88], rdx
0x180006726  mov     [rsp+0B8h+var_90], rdx
0x18000672b  jmp     short loc_180006759
0x18000672d  lea     rcx, [rsp+0B8h+var_58]
0x180006732  mov     r8d, 1
0x180006738  mov     [rsp+0B8h+var_68], rcx
0x18000673d  mov     [rsp+0B8h+var_70], rbx
0x180006742  mov     [rsp+0B8h+var_78], rdi
0x180006747  mov     [rsp+0B8h+var_80], rdx
0x18000674c  mov     rdx, rbp
0x18000674f  mov     [rsp+0B8h+var_88], r13
0x180006754  mov     [rsp+0B8h+var_90], r12
0x180006759  mov     rax, [r14]
0x18000675c  mov     r9, rsi
0x18000675f  mov     rcx, r14
0x180006762  mov     [rsp+0B8h+var_98], r15d
0x180006767  mov     rax, [rax+50h]
0x18000676b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006770  test    eax, eax
0x180006772  js      short loc_180006788
0x180006774  cmp     [rsp+0B8h+var_58], 2
0x180006779  mov     ecx, 80073701h
0x18000677e  cmovz   eax, ecx
0x180006781  jmp     short loc_180006788
0x180006783  mov     eax, 80070057h
0x180006788  mov     rcx, [rsp+0B8h+var_50]
0x18000678d  xor     rcx, rsp; StackCookie
0x180006790  call    __security_check_cookie
0x180006795  add     rsp, 78h
0x180006799  pop     r15
0x18000679b  pop     r14
0x18000679d  pop     r13
0x18000679f  pop     r12
0x1800067a1  pop     rdi
0x1800067a2  pop     rsi
0x1800067a3  pop     rbp
0x1800067a4  pop     rbx
0x1800067a5  retn
```
