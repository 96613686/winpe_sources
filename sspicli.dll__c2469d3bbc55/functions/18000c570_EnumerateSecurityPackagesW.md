# EnumerateSecurityPackagesW

- ea: `0x18000c570`
- end: `0x18000c638`
- name: `EnumerateSecurityPackagesW`
- size: `200`
- prototype: `SECURITY_STATUS __stdcall(unsigned int *pcPackages, PSecPkgInfoW *ppPackageInfo)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003ee0`
- `0x18000c570`
- `0x18000c640`
- `0x18001b020`
- `0x18001b048`

## pseudocode

```c
SECURITY_STATUS __stdcall EnumerateSecurityPackagesW(unsigned int *pcPackages, PSecPkgInfoW *ppPackageInfo)
{
  SECURITY_STATUS v4; // ebx
  HLOCAL *v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  v4 = SecLocatePackageById(0, &v6);
  if ( v4 >= 0 )
  {
    if ( (unsigned int)SecEnumeratePackagesW(pcPackages, ppPackageInfo) )
    {
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids);
      return -2146893056;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        &WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids,
        (unsigned int)v4);
    if ( v4 == -2146893055 )
      return -2146893051;
    return v4;
  }
}

```

## disassembly

```asm
0x18000c570  mov     rax, rsp
0x18000c573  mov     [rax+8], rbx
0x18000c577  mov     [rax+10h], rsi
0x18000c57b  push    rdi
0x18000c57c  sub     rsp, 20h
0x18000c580  mov     rdi, rdx
0x18000c583  mov     qword ptr [rax+18h], 0
0x18000c58b  mov     rsi, rcx
0x18000c58e  lea     rdx, [rax+18h]
0x18000c592  xor     ecx, ecx
0x18000c594  call    SecLocatePackageById
0x18000c599  mov     ebx, eax
0x18000c59b  test    eax, eax
0x18000c59d  jns     short loc_18000C5E2
0x18000c59f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5a6  lea     rax, WPP_GLOBAL_Control
0x18000c5ad  cmp     rcx, rax
0x18000c5b0  jz      short loc_18000C5D0
0x18000c5b2  test    byte ptr [rcx+1Ch], 1
0x18000c5b6  jz      short loc_18000C5D0
0x18000c5b8  mov     rcx, [rcx+10h]
0x18000c5bc  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x18000c5c3  mov     edx, 1Eh
0x18000c5c8  mov     r9d, ebx
0x18000c5cb  call    WPP_SF_D
0x18000c5d0  mov     eax, 80090305h
0x18000c5d5  cmp     ebx, 80090301h
0x18000c5db  cmovz   ebx, eax
0x18000c5de  mov     eax, ebx
0x18000c5e0  jmp     short loc_18000C628
0x18000c5e2  mov     rdx, rdi
0x18000c5e5  mov     rcx, rsi
0x18000c5e8  call    SecEnumeratePackagesW
0x18000c5ed  test    eax, eax
0x18000c5ef  jz      short loc_18000C5F5
0x18000c5f1  xor     eax, eax
0x18000c5f3  jmp     short loc_18000C628
0x18000c5f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5fc  lea     rax, WPP_GLOBAL_Control
0x18000c603  cmp     rcx, rax
0x18000c606  jz      short loc_18000C623
0x18000c608  test    byte ptr [rcx+1Ch], 1
0x18000c60c  jz      short loc_18000C623
0x18000c60e  mov     rcx, [rcx+10h]
0x18000c612  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x18000c619  mov     edx, 1Fh
0x18000c61e  call    WPP_SF_
0x18000c623  mov     eax, 80090300h
0x18000c628  mov     rbx, [rsp+28h+arg_0]
0x18000c62d  mov     rsi, [rsp+28h+arg_8]
0x18000c632  add     rsp, 20h
0x18000c636  pop     rdi
0x18000c637  retn
```
