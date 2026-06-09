# BLB_SD_INFO::Initialize(void *)

- ea: `0x1400f01e4`
- end: `0x1400f0465`
- name: `?Initialize@BLB_SD_INFO@@QEAAJPEAX@Z`
- size: `641`
- prototype: `__int64 __fastcall(PSID *pOwner, void *Src)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400f046c`

## callees

- `0x14000bb24`
- `0x14000bb4c`
- `0x14000cbcc`
- `0x1400f01e4`
- `0x140134cd2`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400f03d0`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x1400f03d0`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x1400f0374`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x1400f0374`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x1400f0252`
- `ADVAPI32!GetSecurityDescriptorControl` at `0x1400f0252`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1400f02f7`
- `ADVAPI32!GetSecurityDescriptorLength` at `0x1400f02f7`
- `KERNEL32!GetLastError` at `0x1400f025c`
- `KERNEL32!GetLastError` at `0x1400f037e`
- `KERNEL32!GetLastError` at `0x1400f03da`
- `KERNEL32!GetLastError` at `0x1400f025c`
- `KERNEL32!GetLastError` at `0x1400f037e`
- `KERNEL32!GetLastError` at `0x1400f03da`
- `ole32!CoTaskMemFree` at `0x1400f0423`
- `ole32!CoTaskMemFree` at `0x1400f0423`

## pseudocode

```c
__int64 __fastcall BLB_SD_INFO::Initialize(PSID *pOwner, void *Src)
{
  signed int v4; // eax
  unsigned int v5; // ebx
  PVOID *v6; // rcx
  DWORD SecurityDescriptorLength; // eax
  size_t v8; // rbp
  PSECURITY_DESCRIPTOR v9; // rdi
  const void *v10; // rdx
  signed int v11; // eax
  __int64 v12; // rdx
  signed int LastError; // eax
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+20h] [rbp-38h] BYREF
  WORD pControl; // [rsp+70h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+78h] [rbp+20h] BYREF

  dwRevision = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_69eba809750e303923687b65610740a4_Traceguids);
  }
  pControl = 0;
  pSecurityDescriptor = 0;
  if ( GetSecurityDescriptorControl(Src, &pControl, &dwRevision) )
  {
    if ( (pControl & 0x8000u) == 0 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_69eba809750e303923687b65610740a4_Traceguids);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      v5 = -2147024809;
      goto LABEL_44;
    }
    SecurityDescriptorLength = GetSecurityDescriptorLength(Src);
    v8 = SecurityDescriptorLength;
    v5 = BlbutilMemalloc(&pSecurityDescriptor, 1u, SecurityDescriptorLength);
    if ( (v5 & 0x80000000) != 0 )
    {
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        v9 = pSecurityDescriptor;
        goto LABEL_41;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_69eba809750e303923687b65610740a4_Traceguids);
      v9 = pSecurityDescriptor;
      goto LABEL_40;
    }
    v10 = Src;
    v9 = pSecurityDescriptor;
    memcpy_0(pSecurityDescriptor, v10, v8);
    if ( GetSecurityDescriptorOwner(v9, pOwner, (LPBOOL)pOwner + 2) )
    {
      if ( GetSecurityDescriptorDacl(v9, (LPBOOL)pOwner + 7, (PACL *)pOwner + 2, (LPBOOL)pOwner + 6) )
      {
        pOwner[4] = v9;
        v9 = 0;
        goto LABEL_40;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 15;
        goto LABEL_31;
      }
    }
    else
    {
      v11 = GetLastError();
      v5 = v11;
      if ( v11 > 0 )
        v5 = (unsigned __int16)v11 | 0x80070000;
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = 14;
LABEL_31:
        WPP_SF_d(v6[2], v12, WPP_69eba809750e303923687b65610740a4_Traceguids);
LABEL_40:
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
LABEL_41:
    if ( v9 )
    {
      CoTaskMemFree(v9);
      goto LABEL_43;
    }
LABEL_44:
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 4u )
      WPP_SF_(v6[2], 16, WPP_69eba809750e303923687b65610740a4_Traceguids);
    return v5;
  }
  v4 = GetLastError();
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_69eba809750e303923687b65610740a4_Traceguids);
LABEL_43:
      v6 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  return v5;
}

```

## disassembly

```asm
0x1400f01e4  mov     [rsp+arg_0], rbx
0x1400f01e9  push    rbp
0x1400f01ea  push    rsi
0x1400f01eb  push    rdi
0x1400f01ec  push    r12
0x1400f01ee  push    r15
0x1400f01f0  sub     rsp, 30h
0x1400f01f4  mov     rdi, rdx
0x1400f01f7  mov     [rsp+58h+dwRevision], 0
0x1400f01ff  mov     rsi, rcx
0x1400f0202  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f0209  lea     r15, WPP_GLOBAL_Control
0x1400f0210  lea     r12, WPP_69eba809750e303923687b65610740a4_Traceguids
0x1400f0217  cmp     rcx, r15
0x1400f021a  jz      short loc_1400F0239
0x1400f021c  test    byte ptr [rcx+1Ch], 1
0x1400f0220  jz      short loc_1400F0239
0x1400f0222  cmp     byte ptr [rcx+19h], 4
0x1400f0226  jb      short loc_1400F0239
0x1400f0228  mov     rcx, [rcx+10h]
0x1400f022c  mov     edx, 0Ah
0x1400f0231  mov     r8, r12
0x1400f0234  call    WPP_SF_
0x1400f0239  xor     eax, eax
0x1400f023b  lea     r8, [rsp+58h+dwRevision]; lpdwRevision
0x1400f0240  lea     rdx, [rsp+58h+pControl]; pControl
0x1400f0245  mov     [rsp+58h+pControl], ax
0x1400f024a  mov     rcx, rdi; pSecurityDescriptor
0x1400f024d  mov     [rsp+58h+pSecurityDescriptor], rax
0x1400f0252  call    cs:__imp_GetSecurityDescriptorControl
0x1400f0258  test    eax, eax
0x1400f025a  jnz     short loc_1400F02AE
0x1400f025c  call    cs:__imp_GetLastError
0x1400f0262  mov     ebx, eax
0x1400f0264  test    eax, eax
0x1400f0266  jle     short loc_1400F0271
0x1400f0268  movzx   ebx, ax
0x1400f026b  or      ebx, 80070000h
0x1400f0271  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f0278  cmp     rcx, r15
0x1400f027b  jz      loc_1400F0452
0x1400f0281  test    byte ptr [rcx+1Ch], 1
0x1400f0285  jz      loc_1400F0430
0x1400f028b  cmp     byte ptr [rcx+19h], 2
0x1400f028f  jb      loc_1400F0430
0x1400f0295  mov     rcx, [rcx+10h]
0x1400f0299  mov     edx, 0Bh
0x1400f029e  mov     r9d, ebx
0x1400f02a1  mov     r8, r12
0x1400f02a4  call    WPP_SF_d
0x1400f02a9  jmp     loc_1400F0429
0x1400f02ae  mov     eax, 8000h
0x1400f02b3  test    [rsp+58h+pControl], ax
0x1400f02b8  jnz     short loc_1400F02F4
0x1400f02ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f02c1  cmp     rcx, r15
0x1400f02c4  jz      short loc_1400F02EA
0x1400f02c6  test    byte ptr [rcx+1Ch], 1
0x1400f02ca  jz      short loc_1400F02EA
0x1400f02cc  cmp     byte ptr [rcx+19h], 2
0x1400f02d0  jb      short loc_1400F02EA
0x1400f02d2  mov     rcx, [rcx+10h]
0x1400f02d6  mov     edx, 0Ch
0x1400f02db  mov     r8, r12
0x1400f02de  call    WPP_SF_
0x1400f02e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f02ea  mov     ebx, 80070057h
0x1400f02ef  jmp     loc_1400F0430
0x1400f02f4  mov     rcx, rdi; pSecurityDescriptor
0x1400f02f7  call    cs:__imp_GetSecurityDescriptorLength
0x1400f02fd  mov     edx, 1; unsigned int
0x1400f0302  lea     rcx, [rsp+58h+pSecurityDescriptor]; void **
0x1400f0307  mov     r8d, eax; unsigned int
0x1400f030a  mov     ebp, eax
0x1400f030c  call    ?BlbutilMemalloc@@YAJPEAPEAXKK@Z; BlbutilMemalloc(void * *,ulong,ulong)
0x1400f0311  mov     ebx, eax
0x1400f0313  test    eax, eax
0x1400f0315  jns     short loc_1400F0357
0x1400f0317  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f031e  cmp     rcx, r15
0x1400f0321  jz      short loc_1400F034D
0x1400f0323  test    byte ptr [rcx+1Ch], 1
0x1400f0327  jz      short loc_1400F034D
0x1400f0329  cmp     byte ptr [rcx+19h], 2
0x1400f032d  jb      short loc_1400F034D
0x1400f032f  mov     rcx, [rcx+10h]
0x1400f0333  mov     edx, 0Dh
0x1400f0338  mov     r9d, eax
0x1400f033b  mov     r8, r12
0x1400f033e  call    WPP_SF_d
0x1400f0343  mov     rdi, [rsp+58h+pSecurityDescriptor]
0x1400f0348  jmp     loc_1400F0414
0x1400f034d  mov     rdi, [rsp+58h+pSecurityDescriptor]
0x1400f0352  jmp     loc_1400F041B
0x1400f0357  mov     rdx, rdi; Src
0x1400f035a  mov     r8, rbp; Size
0x1400f035d  mov     rdi, [rsp+58h+pSecurityDescriptor]
0x1400f0362  mov     rcx, rdi; void *
0x1400f0365  call    memcpy_0
0x1400f036a  lea     r8, [rsi+8]; lpbOwnerDefaulted
0x1400f036e  mov     rdx, rsi; pOwner
0x1400f0371  mov     rcx, rdi; pSecurityDescriptor
0x1400f0374  call    cs:__imp_GetSecurityDescriptorOwner
0x1400f037a  test    eax, eax
0x1400f037c  jnz     short loc_1400F03C1
0x1400f037e  call    cs:__imp_GetLastError
0x1400f0384  mov     ebx, eax
0x1400f0386  test    eax, eax
0x1400f0388  jle     short loc_1400F0393
0x1400f038a  movzx   ebx, ax
0x1400f038d  or      ebx, 80070000h
0x1400f0393  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f039a  cmp     rcx, r15
0x1400f039d  jz      short loc_1400F041B
0x1400f039f  test    byte ptr [rcx+1Ch], 1
0x1400f03a3  jz      short loc_1400F041B
0x1400f03a5  cmp     byte ptr [rcx+19h], 2
0x1400f03a9  jb      short loc_1400F041B
0x1400f03ab  mov     edx, 0Eh
0x1400f03b0  mov     rcx, [rcx+10h]
0x1400f03b4  mov     r9d, ebx
0x1400f03b7  mov     r8, r12
0x1400f03ba  call    WPP_SF_d
0x1400f03bf  jmp     short loc_1400F0414
0x1400f03c1  lea     r9, [rsi+18h]; lpbDaclDefaulted
0x1400f03c5  mov     rcx, rdi; pSecurityDescriptor
0x1400f03c8  lea     r8, [rsi+10h]; pDacl
0x1400f03cc  lea     rdx, [rsi+1Ch]; lpbDaclPresent
0x1400f03d0  call    cs:__imp_GetSecurityDescriptorDacl
0x1400f03d6  test    eax, eax
0x1400f03d8  jnz     short loc_1400F040E
0x1400f03da  call    cs:__imp_GetLastError
0x1400f03e0  mov     ebx, eax
0x1400f03e2  test    eax, eax
0x1400f03e4  jle     short loc_1400F03EF
0x1400f03e6  movzx   ebx, ax
0x1400f03e9  or      ebx, 80070000h
0x1400f03ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f03f6  cmp     rcx, r15
0x1400f03f9  jz      short loc_1400F041B
0x1400f03fb  test    byte ptr [rcx+1Ch], 1
0x1400f03ff  jz      short loc_1400F041B
0x1400f0401  cmp     byte ptr [rcx+19h], 2
0x1400f0405  jb      short loc_1400F041B
0x1400f0407  mov     edx, 0Fh
0x1400f040c  jmp     short loc_1400F03B0
0x1400f040e  mov     [rsi+20h], rdi
0x1400f0412  xor     edi, edi
0x1400f0414  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f041b  test    rdi, rdi
0x1400f041e  jz      short loc_1400F0430
0x1400f0420  mov     rcx, rdi; pv
0x1400f0423  call    cs:__imp_CoTaskMemFree
0x1400f0429  mov     rcx, cs:WPP_GLOBAL_Control
0x1400f0430  cmp     rcx, r15
0x1400f0433  jz      short loc_1400F0452
0x1400f0435  test    byte ptr [rcx+1Ch], 1
0x1400f0439  jz      short loc_1400F0452
0x1400f043b  cmp     byte ptr [rcx+19h], 4
0x1400f043f  jb      short loc_1400F0452
0x1400f0441  mov     rcx, [rcx+10h]
0x1400f0445  mov     edx, 10h
0x1400f044a  mov     r8, r12
0x1400f044d  call    WPP_SF_
0x1400f0452  mov     eax, ebx
0x1400f0454  mov     rbx, [rsp+58h+arg_0]
0x1400f0459  add     rsp, 30h
0x1400f045d  pop     r15
0x1400f045f  pop     r12
0x1400f0461  pop     rdi
0x1400f0462  pop     rsi
0x1400f0463  pop     rbp
0x1400f0464  retn
```
