# OncRpcSepQuerySizesFromContext

- ea: `0x14000c470`
- end: `0x14000c564`
- name: `OncRpcSepQuerySizesFromContext`
- size: `244`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000bb64`

## callees

- `0x1400020c0`
- `0x14000a1ec`
- `0x14000c470`
- `0x140015640`

## import_xrefs

- `ksecdd!QueryContextAttributesW` at `0x14000c4a5`
- `ksecdd!QueryContextAttributesW` at `0x14000c4a5`
- `ksecdd!MapSecurityError` at `0x14000c4b5`
- `ksecdd!MapSecurityError` at `0x14000c4b5`

## pseudocode

```c
__int64 __fastcall OncRpcSepQuerySizesFromContext(__int64 a1, _DWORD *a2)
{
  unsigned int v4; // esi
  NTSTATUS v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // eax
  __int128 pBuffer; // [rsp+20h] [rbp-38h] BYREF

  pBuffer = 0;
  v4 = QueryContextAttributesW((PCtxtHandle)(a1 + 88), 0, &pBuffer);
  v5 = MapSecurityError(v4);
  if ( v5 >= 0 )
  {
    v6 = HIDWORD(pBuffer) + (-HIDWORD(pBuffer) & 3);
    *(_DWORD *)(a1 + 124) = pBuffer + (-(int)pBuffer & 3);
    v7 = DWORD1(pBuffer);
    *(_DWORD *)(a1 + 116) = v6;
    v8 = -DWORD2(pBuffer) & 3;
    *(_DWORD *)(a1 + 128) = DWORD1(pBuffer) + (-v7 & 3);
    *(_DWORD *)(a1 + 120) = DWORD2(pBuffer) + v8;
  }
  *a2 = OncRpcSeSecStatusToGssMajor(v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000c470  mov     [rsp+arg_10], rbx
0x14000c475  push    rsi
0x14000c476  push    rdi
0x14000c477  push    r14
0x14000c479  sub     rsp, 40h
0x14000c47d  mov     rax, cs:__security_cookie
0x14000c484  xor     rax, rsp
0x14000c487  mov     [rsp+58h+var_28], rax
0x14000c48c  mov     r14, rdx
0x14000c48f  lea     r8, [rsp+58h+pBuffer]; pBuffer
0x14000c494  mov     rdi, rcx
0x14000c497  xorps   xmm0, xmm0
0x14000c49a  add     rcx, 58h ; 'X'; phContext
0x14000c49e  xor     edx, edx; ulAttribute
0x14000c4a0  movups  [rsp+58h+pBuffer], xmm0
0x14000c4a5  call    cs:__imp_QueryContextAttributesW
0x14000c4ac  nop     dword ptr [rax+rax+00h]
0x14000c4b1  mov     ecx, eax; SecStatus
0x14000c4b3  mov     esi, eax
0x14000c4b5  call    cs:__imp_MapSecurityError
0x14000c4bc  nop     dword ptr [rax+rax+00h]
0x14000c4c1  mov     ebx, eax
0x14000c4c3  test    eax, eax
0x14000c4c5  js      short loc_14000C50A
0x14000c4c7  mov     ecx, dword ptr [rsp+58h+pBuffer]
0x14000c4cb  mov     eax, dword ptr [rsp+58h+pBuffer+0Ch]
0x14000c4cf  neg     ecx
0x14000c4d1  and     ecx, 3
0x14000c4d4  neg     eax
0x14000c4d6  add     ecx, dword ptr [rsp+58h+pBuffer]
0x14000c4da  and     eax, 3
0x14000c4dd  add     eax, dword ptr [rsp+58h+pBuffer+0Ch]
0x14000c4e1  mov     [rdi+7Ch], ecx
0x14000c4e4  mov     ecx, dword ptr [rsp+58h+pBuffer+4]
0x14000c4e8  mov     [rdi+74h], eax
0x14000c4eb  neg     ecx
0x14000c4ed  mov     eax, dword ptr [rsp+58h+pBuffer+8]
0x14000c4f1  and     ecx, 3
0x14000c4f4  add     ecx, dword ptr [rsp+58h+pBuffer+4]
0x14000c4f8  neg     eax
0x14000c4fa  and     eax, 3
0x14000c4fd  mov     [rdi+80h], ecx
0x14000c503  add     eax, dword ptr [rsp+58h+pBuffer+8]
0x14000c507  mov     [rdi+78h], eax
0x14000c50a  mov     ecx, esi
0x14000c50c  call    OncRpcSeSecStatusToGssMajor
0x14000c511  mov     [r14], eax
0x14000c514  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c51b  lea     rax, WPP_GLOBAL_Control
0x14000c522  cmp     rcx, rax
0x14000c525  jz      short loc_14000C546
0x14000c527  mov     eax, [rcx+2Ch]
0x14000c52a  test    al, 1
0x14000c52c  jz      short loc_14000C546
0x14000c52e  mov     rcx, [rcx+18h]
0x14000c532  lea     r8, WPP_e26fb84b27c236afaa3664beb63ddb12_Traceguids
0x14000c539  mov     edx, 1Eh
0x14000c53e  mov     r9d, ebx
0x14000c541  call    WPP_SF_d
0x14000c546  mov     eax, ebx
0x14000c548  mov     rcx, [rsp+58h+var_28]
0x14000c54d  xor     rcx, rsp; StackCookie
0x14000c550  call    __security_check_cookie
0x14000c555  mov     rbx, [rsp+58h+arg_10]
0x14000c55a  add     rsp, 40h
0x14000c55e  pop     r14
0x14000c560  pop     rdi
0x14000c561  pop     rsi
0x14000c562  retn
```
