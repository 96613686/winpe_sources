# SrpCheckSmartlockerEAandProcessToken2

- ea: `0x180047070`
- end: `0x180047277`
- name: `SrpCheckSmartlockerEAandProcessToken2`
- size: `519`
- prototype: `__int64 __fastcall(void *, __int64, _DWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180040550`
- `0x180047060`

## callees

- `0x180047070`
- `0x1800473f0`
- `0x18004de52`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047153`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047226`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047153`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180047226`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004719d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047205`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047252`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047260`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004719d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047205`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047252`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047260`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004710c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004710c`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180047185`
- `ntdll!NtQuerySecurityAttributesToken` at `0x180047185`

## string_xrefs

- `0x1800470fc`: `System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
__int64 __fastcall SrpCheckSmartlockerEAandProcessToken2(void *a1, __int64 a2, _DWORD *a3, _QWORD *a4)
{
  unsigned int v7; // ebx
  _DWORD *v8; // r14
  HLOCAL v9; // rdi
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // ecx
  unsigned int v14; // ebx
  unsigned int v15; // esi
  HLOCAL v16; // rax
  int v18; // [rsp+40h] [rbp-20h]
  unsigned int v19; // [rsp+44h] [rbp-1Ch] BYREF
  SIZE_T uBytes; // [rsp+48h] [rbp-18h]
  __int64 v21; // [rsp+50h] [rbp-10h]
  HLOCAL hMem; // [rsp+58h] [rbp-8h]

  uBytes = 0x400000248LL;
  v21 = 0;
  hMem = 0;
  v19 = 0;
  v18 = 0;
  v7 = 694;
  SrpSmartlockerGetValidEA(a1);
  v8 = 0;
  while ( 1 )
  {
    v9 = LocalAlloc(0x40u, v7);
    if ( !v9 )
      goto LABEL_22;
    v10 = NtQuerySecurityAttributesToken(a2, L"24", 1, v9, v7, &v19);
    if ( v10 != -1073741789 )
      break;
    if ( v7 >= v19 )
      goto LABEL_16;
    v7 = v19;
    LocalFree(v9);
  }
  if ( v10 < 0 )
  {
LABEL_16:
    LocalFree(v9);
    v9 = 0;
    goto LABEL_17;
  }
  if ( !*((_DWORD *)v9 + 1) )
    goto LABEL_17;
  v11 = *((_QWORD *)v9 + 1);
  if ( *(_WORD *)(v11 + 16) != 16 )
    goto LABEL_17;
  v12 = *(_QWORD *)(v11 + 32);
  if ( *(_DWORD *)(v12 + 8) < 0x40u )
    goto LABEL_17;
  v8 = *(_DWORD **)v12;
  LODWORD(uBytes) = *(_DWORD *)(v12 + 8);
  if ( v8[2] == 2 || v8[2] > 4u )
    goto LABEL_17;
  v13 = v8[1];
  v14 = 0;
  if ( !v13 )
  {
    *a3 |= 0x4001u;
    goto LABEL_18;
  }
  if ( v13 != 1 )
  {
LABEL_17:
    v14 = -1073741823;
    goto LABEL_18;
  }
  *a3 |= 0x2000u;
LABEL_18:
  if ( *a3 )
  {
    v14 = 0;
    if ( a4 )
    {
      v15 = uBytes;
      v16 = LocalAlloc(0x40u, (unsigned int)uBytes);
      *a4 = v16;
      if ( v16 )
      {
        memcpy_0(v16, v8, v15);
        goto LABEL_23;
      }
LABEL_22:
      v14 = -1073741801;
    }
  }
LABEL_23:
  if ( hMem )
    LocalFree(hMem);
  if ( v9 )
    LocalFree(v9);
  return v14;
}

```

## disassembly

```asm
0x180047070  push    rbp
0x180047072  push    rbx
0x180047073  push    rsi
0x180047074  push    rdi
0x180047075  push    r12
0x180047077  push    r14
0x180047079  push    r15
0x18004707b  mov     rbp, rsp
0x18004707e  sub     rsp, 60h
0x180047082  mov     r15, r9
0x180047085  mov     dword ptr [rbp+uBytes], 248h
0x18004708c  mov     rsi, r8
0x18004708f  mov     [rbp+var_10], 0
0x180047097  mov     r12, rdx
0x18004709a  mov     [rbp+hMem], 0
0x1800470a2  lea     r9, [rbp+hMem]
0x1800470a6  mov     [rbp+var_1C], 0
0x1800470ad  lea     r8, [rbp+var_10]
0x1800470b1  mov     [rbp+var_20], 0
0x1800470b8  lea     rdx, [rbp+uBytes]
0x1800470bc  mov     dword ptr [rbp+uBytes+4], 4
0x1800470c3  mov     ebx, 2B6h
0x1800470c8  call    SrpSmartlockerGetValidEA
0x1800470cd  mov     r14, [rbp+var_10]
0x1800470d1  test    r14, r14
0x1800470d4  jz      short loc_18004714C
0x1800470d6  lea     rax, [rbp+uBytes+4]
0x1800470da  mov     r9d, 10h; dwFlags
0x1800470e0  mov     [rsp+60h+pcbData], rax; pcbData
0x1800470e5  lea     r8, aTrustedorigind; "TrustedOriginDataId"
0x1800470ec  lea     rax, [rbp+var_20]
0x1800470f0  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800470f7  mov     [rsp+60h+pvData], rax; pvData
0x1800470fc  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\App"...
0x180047103  mov     [rsp+60h+pdwType], 0; pdwType
0x18004710c  call    cs:__imp_RegGetValueW
0x180047112  test    eax, eax
0x180047114  jz      short loc_18004711D
0x180047116  xor     eax, eax
0x180047118  mov     [rbp+var_20], eax
0x18004711b  jmp     short loc_180047120
0x18004711d  mov     eax, [rbp+var_20]
0x180047120  cmp     [r14+34h], eax
0x180047124  jb      short loc_18004714C
0x180047126  mov     eax, [r14+8]
0x18004712a  cmp     eax, 1
0x18004712d  jbe     short loc_180047137
0x18004712f  add     eax, 0FFFFFFFDh
0x180047132  cmp     eax, 1
0x180047135  ja      short loc_18004714C
0x180047137  mov     ecx, [r14+4]
0x18004713b  test    ecx, ecx
0x18004713d  jz      short loc_180047149
0x18004713f  cmp     ecx, 1
0x180047142  jnz     short loc_18004714C
0x180047144  or      dword ptr [rsi], 2
0x180047147  jmp     short loc_18004714C
0x180047149  or      dword ptr [rsi], 1
0x18004714c  mov     edx, ebx; uBytes
0x18004714e  mov     ecx, 40h ; '@'; uFlags
0x180047153  call    cs:__imp_LocalAlloc
0x180047159  mov     rdi, rax
0x18004715c  test    rax, rax
0x18004715f  jz      loc_180047244
0x180047165  lea     rax, [rbp+var_1C]
0x180047169  mov     r9, rdi
0x18004716c  mov     [rsp+60h+pvData], rax
0x180047171  lea     rdx, a24; "24"
0x180047178  mov     r8d, 1
0x18004717e  mov     dword ptr [rsp+60h+pdwType], ebx
0x180047182  mov     rcx, r12
0x180047185  call    cs:__imp_NtQuerySecurityAttributesToken
0x18004718b  cmp     eax, 0C0000023h
0x180047190  jnz     short loc_1800471A5
0x180047192  cmp     ebx, [rbp+var_1C]
0x180047195  jnb     short loc_180047202
0x180047197  mov     ebx, [rbp+var_1C]
0x18004719a  mov     rcx, rdi; hMem
0x18004719d  call    cs:__imp_LocalFree
0x1800471a3  jmp     short loc_18004714C
0x1800471a5  test    eax, eax
0x1800471a7  js      short loc_180047202
0x1800471a9  cmp     dword ptr [rdi+4], 0
0x1800471ad  jbe     short loc_18004720D
0x1800471af  mov     rax, [rdi+8]
0x1800471b3  mov     ecx, 10h
0x1800471b8  cmp     [rax+10h], cx
0x1800471bc  jnz     short loc_18004720D
0x1800471be  mov     rcx, [rax+20h]
0x1800471c2  mov     eax, [rcx+8]
0x1800471c5  cmp     eax, 40h ; '@'
0x1800471c8  jb      short loc_18004720D
0x1800471ca  mov     r14, [rcx]
0x1800471cd  mov     dword ptr [rbp+uBytes], eax
0x1800471d0  cmp     dword ptr [r14+8], 2
0x1800471d5  jz      short loc_18004720D
0x1800471d7  cmp     dword ptr [r14+8], 0FFFFFFFFh
0x1800471dc  jle     short loc_18004720D
0x1800471de  cmp     dword ptr [r14+8], 5
0x1800471e3  jge     short loc_18004720D
0x1800471e5  mov     ecx, [r14+4]
0x1800471e9  xor     ebx, ebx
0x1800471eb  test    ecx, ecx
0x1800471ed  jz      short loc_1800471FA
0x1800471ef  cmp     ecx, 1
0x1800471f2  jnz     short loc_18004720D
0x1800471f4  bts     dword ptr [rsi], 0Dh
0x1800471f8  jmp     short loc_180047212
0x1800471fa  or      dword ptr [rsi], 4001h
0x180047200  jmp     short loc_180047212
0x180047202  mov     rcx, rdi; hMem
0x180047205  call    cs:__imp_LocalFree
0x18004720b  xor     edi, edi
0x18004720d  mov     ebx, 0C0000001h
0x180047212  cmp     dword ptr [rsi], 0
0x180047215  jz      short loc_180047249
0x180047217  xor     ebx, ebx
0x180047219  test    r15, r15
0x18004721c  jz      short loc_180047249
0x18004721e  mov     esi, dword ptr [rbp+uBytes]
0x180047221  lea     ecx, [rbx+40h]; uFlags
0x180047224  mov     edx, esi; uBytes
0x180047226  call    cs:__imp_LocalAlloc
0x18004722c  mov     [r15], rax
0x18004722f  test    rax, rax
0x180047232  jz      short loc_180047244
0x180047234  mov     r8d, esi; Size
0x180047237  mov     rdx, r14; Src
0x18004723a  mov     rcx, rax; void *
0x18004723d  call    memcpy_0
0x180047242  jmp     short loc_180047249
0x180047244  mov     ebx, 0C0000017h
0x180047249  mov     rcx, [rbp+hMem]; hMem
0x18004724d  test    rcx, rcx
0x180047250  jz      short loc_180047258
0x180047252  call    cs:__imp_LocalFree
0x180047258  test    rdi, rdi
0x18004725b  jz      short loc_180047266
0x18004725d  mov     rcx, rdi; hMem
0x180047260  call    cs:__imp_LocalFree
0x180047266  mov     eax, ebx
0x180047268  add     rsp, 60h
0x18004726c  pop     r15
0x18004726e  pop     r14
0x180047270  pop     r12
0x180047272  pop     rdi
0x180047273  pop     rsi
0x180047274  pop     rbx
0x180047275  pop     rbp
0x180047276  retn
```
