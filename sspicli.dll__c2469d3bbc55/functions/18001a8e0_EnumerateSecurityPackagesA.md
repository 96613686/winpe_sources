# EnumerateSecurityPackagesA

- ea: `0x18001a8e0`
- end: `0x18001a9a8`
- name: `EnumerateSecurityPackagesA`
- size: `200`
- prototype: `SECURITY_STATUS __stdcall(unsigned int *pcPackages, PSecPkgInfoA *ppPackageInfo)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003ee0`
- `0x180014d98`
- `0x18001a8e0`
- `0x18001b020`
- `0x18001b048`

## pseudocode

```c
SECURITY_STATUS __stdcall EnumerateSecurityPackagesA(unsigned int *pcPackages, PSecPkgInfoA *ppPackageInfo)
{
  SECURITY_STATUS v4; // ebx
  HLOCAL *v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  v4 = SecLocatePackageById(0, &v6);
  if ( v4 >= 0 )
  {
    if ( (unsigned int)SecEnumeratePackagesA(pcPackages, ppPackageInfo) )
    {
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids);
      return -2146893056;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
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
0x18001a8e0  mov     rax, rsp
0x18001a8e3  mov     [rax+8], rbx
0x18001a8e7  mov     [rax+10h], rsi
0x18001a8eb  push    rdi
0x18001a8ec  sub     rsp, 20h
0x18001a8f0  mov     rdi, rdx
0x18001a8f3  mov     qword ptr [rax+18h], 0
0x18001a8fb  mov     rsi, rcx
0x18001a8fe  lea     rdx, [rax+18h]
0x18001a902  xor     ecx, ecx
0x18001a904  call    SecLocatePackageById
0x18001a909  mov     ebx, eax
0x18001a90b  test    eax, eax
0x18001a90d  jns     short loc_18001A952
0x18001a90f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a916  lea     rax, WPP_GLOBAL_Control
0x18001a91d  cmp     rcx, rax
0x18001a920  jz      short loc_18001A940
0x18001a922  test    byte ptr [rcx+1Ch], 1
0x18001a926  jz      short loc_18001A940
0x18001a928  mov     rcx, [rcx+10h]
0x18001a92c  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x18001a933  mov     edx, 20h ; ' '
0x18001a938  mov     r9d, ebx
0x18001a93b  call    WPP_SF_D
0x18001a940  mov     eax, 80090305h
0x18001a945  cmp     ebx, 80090301h
0x18001a94b  cmovz   ebx, eax
0x18001a94e  mov     eax, ebx
0x18001a950  jmp     short loc_18001A998
0x18001a952  mov     rdx, rdi
0x18001a955  mov     rcx, rsi
0x18001a958  call    SecEnumeratePackagesA
0x18001a95d  test    eax, eax
0x18001a95f  jz      short loc_18001A965
0x18001a961  xor     eax, eax
0x18001a963  jmp     short loc_18001A998
0x18001a965  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a96c  lea     rax, WPP_GLOBAL_Control
0x18001a973  cmp     rcx, rax
0x18001a976  jz      short loc_18001A993
0x18001a978  test    byte ptr [rcx+1Ch], 1
0x18001a97c  jz      short loc_18001A993
0x18001a97e  mov     rcx, [rcx+10h]
0x18001a982  lea     r8, WPP_840462f8282031f1d86bf34f3d7cbc6c_Traceguids
0x18001a989  mov     edx, 21h ; '!'
0x18001a98e  call    WPP_SF_
0x18001a993  mov     eax, 80090300h
0x18001a998  mov     rbx, [rsp+28h+arg_0]
0x18001a99d  mov     rsi, [rsp+28h+arg_8]
0x18001a9a2  add     rsp, 20h
0x18001a9a6  pop     rdi
0x18001a9a7  retn
```
