# VsmmDaxFilepLockContextSetup

- ea: `0x1400bce20`
- end: `0x1400bd2f1`
- name: `VsmmDaxFilepLockContextSetup`
- size: `1233`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400bc0c4`

## callees

- `0x1400029c0`
- `0x140006b68`
- `0x14000a010`
- `0x140021c60`
- `0x1400386a0`
- `0x1400bce20`
- `0x1400bd2f8`
- `0x1400bdf00`
- `0x1400be484`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bcf50`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bcf50`
- `ntoskrnl!ZwClose` at `0x1400bd1c2`
- `ntoskrnl!ZwClose` at `0x1400bd1c2`
- `ntoskrnl!ZwCreateSection` at `0x1400bcefe`
- `ntoskrnl!ZwCreateSection` at `0x1400bcefe`
- `ntoskrnl!RtlGetNonVolatileToken` at `0x1400bd01e`
- `ntoskrnl!RtlGetNonVolatileToken` at `0x1400bd01e`

## pseudocode

```c
__int64 __fastcall VsmmDaxFilepLockContextSetup(__int64 a1, __int64 a2, HANDLE *a3, unsigned __int64 a4, __int64 a5)
{
  unsigned __int64 v5; // r15
  NTSTATUS NonVolatileToken; // edi
  _BYTE *v9; // r14
  unsigned int i; // eax
  __int64 v11; // rcx
  __int64 v12; // r12
  __int64 v13; // r12
  PVOID v14; // r15
  PVOID Object; // [rsp+40h] [rbp-168h] BYREF
  _QWORD *v17; // [rsp+48h] [rbp-160h] BYREF
  NTSTATUS v18; // [rsp+50h] [rbp-158h]
  void *SectionHandle; // [rsp+58h] [rbp-150h] BYREF
  __int64 v20; // [rsp+60h] [rbp-148h] BYREF
  __int64 v21; // [rsp+68h] [rbp-140h] BYREF
  HANDLE *v22; // [rsp+70h] [rbp-138h] BYREF
  __int64 v23; // [rsp+78h] [rbp-130h]
  void *v24; // [rsp+80h] [rbp-128h] BYREF
  HANDLE *v25; // [rsp+88h] [rbp-120h]
  HANDLE *v26; // [rsp+90h] [rbp-118h]
  __int64 v27; // [rsp+98h] [rbp-110h]
  __int64 v28; // [rsp+A0h] [rbp-108h]
  _BYTE *v29; // [rsp+B0h] [rbp-F8h]
  struct _OBJECT_ATTRIBUTES v30; // [rsp+B8h] [rbp-F0h] BYREF
  _BYTE v31[32]; // [rsp+F0h] [rbp-B8h] BYREF
  _BYTE v32[16]; // [rsp+110h] [rbp-98h] BYREF
  _BYTE v33[16]; // [rsp+120h] [rbp-88h] BYREF
  _QWORD **v34; // [rsp+130h] [rbp-78h]
  __int64 v35; // [rsp+138h] [rbp-70h]
  PVOID *p_Object; // [rsp+140h] [rbp-68h]
  __int64 v37; // [rsp+148h] [rbp-60h]
  HANDLE **v38; // [rsp+150h] [rbp-58h]
  __int64 v39; // [rsp+158h] [rbp-50h]

  v5 = a4;
  v25 = a3;
  v17 = (_QWORD *)a1;
  v26 = a3;
  v27 = a1;
  v22 = a3;
  v28 = a5;
  *(_QWORD *)&v30.Length = 48;
  *(_QWORD *)&v30.Attributes = 512;
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_OWORD *)(a1 + 32) = 0;
  v24 = 0;
  SectionHandle = 0;
  v30.RootDirectory = 0;
  v30.ObjectName = 0;
  *(_OWORD *)&v30.SecurityDescriptor = 0;
  NonVolatileToken = ZwCreateSection(&SectionHandle, 6u, &v30, 0, 4u, 0x8000000u, *a3);
  if ( NonVolatileToken >= 0 )
  {
    Object = 0;
    NonVolatileToken = ObReferenceObjectByHandle(SectionHandle, 4u, 0, 0, &Object, 0);
    *(_QWORD *)(a1 + 8) = Object;
    if ( NonVolatileToken >= 0 )
    {
      v9 = a3 + 4;
      v29 = v9;
      if ( *v9 )
      {
        for ( i = 0; i < v5; ++i )
        {
          if ( !*(_DWORD *)(a5 + 24LL * i) )
          {
            Object = 0;
            v11 = *(_QWORD *)(a5 + 24LL * i + 16) << 12;
            v23 = v11;
            v20 = v11;
            v12 = 16;
            if ( *(_QWORD *)(a5 + 24LL * i + 8) < 0x10u )
              v12 = *(_QWORD *)(a5 + 24LL * i + 8);
            v13 = v12 << 12;
            v21 = v13;
            NonVolatileToken = VsmmDaxFilepMapSystemVa(*(_QWORD *)(a1 + 8), v11, v13, &Object);
            if ( NonVolatileToken >= 0 )
            {
              v14 = Object;
              NonVolatileToken = RtlGetNonVolatileToken(Object, v13, &v24);
              v18 = NonVolatileToken;
              VsmmDaxFilepUnmapSystemVa(v14);
              if ( NonVolatileToken >= 0 )
              {
                v5 = a4;
                break;
              }
              if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
              {
                tlgCreate1Sz_char(v32, "VsmmDaxFilepLockContextSetup");
                tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
                LODWORD(v17) = 1944;
                v34 = &v17;
                v35 = 4;
                v21 = v23;
                p_Object = (PVOID *)&v21;
                v37 = 8;
                v20 = v13;
                v38 = (HANDLE **)&v20;
                v39 = 8;
                tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, qword_140050978, 0, 0, 7, v31);
              }
            }
            goto LABEL_19;
          }
        }
      }
      v22[3] = v24;
      *v17 = a2;
      *(_QWORD *)(a1 + 16) = v5;
      *(_QWORD *)(a1 + 24) = a5;
      *(_QWORD *)(a1 + 32) = VsmmMemoryBlockpAssignPagesFromDaxFileRange;
      *(_BYTE *)(a1 + 40) = *v9;
      NonVolatileToken = 0;
    }
    else
    {
      VidTraceErrorInternal0("VsmmDaxFilepLockContextSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 1892);
    }
  }
  else
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockContextSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 1879);
  }
LABEL_19:
  if ( SectionHandle )
    ZwClose(SectionHandle);
  if ( NonVolatileToken < 0 )
  {
    VsmmDaxFilepLockContextTeardown(a1);
    if ( (unsigned int)dword_140065110 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v32, "VsmmDaxFilepLockContextSetup");
        tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
        LODWORD(v17) = 1975;
        v34 = &v17;
        v35 = 4;
        LODWORD(Object) = NonVolatileToken;
        p_Object = &Object;
        v37 = 4;
        v22 = (HANDLE *)*v25;
        v38 = &v22;
        v39 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, byte_1400509CB, 0, 0, 7, v31);
      }
    }
  }
  return (unsigned int)NonVolatileToken;
}

```

## disassembly

```asm
0x1400bce20  mov     r11, rsp
0x1400bce23  mov     [r11+20h], r9
0x1400bce27  mov     [r11+10h], rdx
0x1400bce2b  push    rbx
0x1400bce2c  push    rsi
0x1400bce2d  push    rdi
0x1400bce2e  push    r12
0x1400bce30  push    r13
0x1400bce32  push    r14
0x1400bce34  push    r15
0x1400bce36  sub     rsp, 170h
0x1400bce3d  mov     rax, cs:__security_cookie
0x1400bce44  xor     rax, rsp
0x1400bce47  mov     [rsp+1A8h+var_48], rax
0x1400bce4f  mov     r15, r9
0x1400bce52  mov     [rsp+1A8h+var_120], r8
0x1400bce5a  mov     [rsp+1A8h+var_160], rcx
0x1400bce5f  mov     [rsp+1A8h+var_118], r8
0x1400bce67  mov     rsi, rcx
0x1400bce6a  mov     [rsp+1A8h+var_110], rcx
0x1400bce72  mov     r14, r8
0x1400bce75  mov     [rsp+1A8h+var_138], r8
0x1400bce7a  mov     r13, [rsp+1A8h+arg_20]
0x1400bce82  mov     [rsp+1A8h+var_108], r13
0x1400bce8a  xor     ebx, ebx
0x1400bce8c  mov     qword ptr [r11-0F0h], 30h ; '0'
0x1400bce97  mov     qword ptr [r11-0D8h], 200h
0x1400bcea2  xorps   xmm0, xmm0
0x1400bcea5  movups  xmmword ptr [rcx], xmm0
0x1400bcea8  movups  xmmword ptr [rcx+10h], xmm0
0x1400bceac  movups  xmmword ptr [rcx+20h], xmm0
0x1400bceb0  mov     [r11-128h], rbx
0x1400bceb7  mov     [rsp+1A8h+SectionHandle], rbx
0x1400bcebc  mov     [r11-0E8h], rbx
0x1400bcec3  mov     [r11-0E0h], rbx
0x1400bceca  movdqu  [rsp+1A8h+var_D0], xmm0
0x1400bced3  mov     rax, [r8]
0x1400bced6  mov     [rsp+1A8h+FileHandle], rax; FileHandle
0x1400bcedb  mov     [rsp+1A8h+AllocationAttributes], 8000000h; AllocationAttributes
0x1400bcee3  lea     r12d, [rbx+4]
0x1400bcee7  mov     [rsp+1A8h+SectionPageProtection], r12d; SectionPageProtection
0x1400bceec  xor     r9d, r9d; MaximumSize
0x1400bceef  lea     r8, [r11-0F0h]; ObjectAttributes
0x1400bcef6  lea     edx, [rbx+6]; DesiredAccess
0x1400bcef9  lea     rcx, [rsp+1A8h+SectionHandle]; SectionHandle
0x1400bcefe  call    cs:__imp_ZwCreateSection
0x1400bcf05  nop     dword ptr [rax+rax+00h]
0x1400bcf0a  mov     edi, eax
0x1400bcf0c  test    eax, eax
0x1400bcf0e  jns     short loc_1400BCF2E
0x1400bcf10  mov     r8d, 757h
0x1400bcf16  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bcf1d  lea     rcx, aVsmmdaxfileplo; "VsmmDaxFilepLockContextSetup"
0x1400bcf24  call    VidTraceErrorInternal0
0x1400bcf29  jmp     loc_1400BD1B8
0x1400bcf2e  mov     [rsp+1A8h+Object], rbx
0x1400bcf33  mov     qword ptr [rsp+1A8h+AllocationAttributes], rbx; HandleInformation
0x1400bcf38  lea     rax, [rsp+1A8h+Object]
0x1400bcf3d  mov     qword ptr [rsp+1A8h+SectionPageProtection], rax; Object
0x1400bcf42  xor     r9d, r9d; AccessMode
0x1400bcf45  xor     r8d, r8d; ObjectType
0x1400bcf48  mov     edx, r12d; DesiredAccess
0x1400bcf4b  mov     rcx, [rsp+1A8h+SectionHandle]; Handle
0x1400bcf50  call    cs:__imp_ObReferenceObjectByHandle
0x1400bcf57  nop     dword ptr [rax+rax+00h]
0x1400bcf5c  mov     edi, eax
0x1400bcf5e  mov     rax, [rsp+1A8h+Object]
0x1400bcf63  mov     [rsi+8], rax
0x1400bcf67  test    edi, edi
0x1400bcf69  jns     short loc_1400BCF89
0x1400bcf6b  mov     r8d, 764h
0x1400bcf71  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bcf78  lea     rcx, aVsmmdaxfileplo; "VsmmDaxFilepLockContextSetup"
0x1400bcf7f  call    VidTraceErrorInternal0
0x1400bcf84  jmp     loc_1400BD1B8
0x1400bcf89  add     r14, 20h ; ' '
0x1400bcf8d  mov     [rsp+1A8h+var_F8], r14
0x1400bcf95  cmp     [r14], bl
0x1400bcf98  jz      loc_1400BD17C
0x1400bcf9e  mov     eax, ebx
0x1400bcfa0  mov     ecx, eax
0x1400bcfa2  cmp     rcx, r15
0x1400bcfa5  jnb     loc_1400BD17C
0x1400bcfab  lea     rdx, [rcx+rcx*2]
0x1400bcfaf  cmp     [r13+rdx*8+0], ebx
0x1400bcfb4  jnz     loc_1400BD16D
0x1400bcfba  mov     [rsp+1A8h+Object], rbx
0x1400bcfbf  mov     rcx, [r13+rdx*8+10h]
0x1400bcfc4  shl     rcx, 0Ch
0x1400bcfc8  mov     [rsp+1A8h+var_130], rcx
0x1400bcfcd  mov     [rsp+1A8h+var_148], rcx
0x1400bcfd2  mov     rax, [r13+rdx*8+8]
0x1400bcfd7  mov     r12d, 10h
0x1400bcfdd  cmp     rax, r12
0x1400bcfe0  cmovb   r12, rax
0x1400bcfe4  shl     r12, 0Ch
0x1400bcfe8  mov     [rsp+1A8h+var_140], r12
0x1400bcfed  lea     r9, [rsp+1A8h+Object]
0x1400bcff2  mov     r8, r12
0x1400bcff5  mov     rdx, rcx
0x1400bcff8  mov     rcx, [rsi+8]
0x1400bcffc  call    VsmmDaxFilepMapSystemVa
0x1400bd001  mov     edi, eax
0x1400bd003  test    eax, eax
0x1400bd005  js      loc_1400BD1B8
0x1400bd00b  lea     r8, [rsp+1A8h+var_128]
0x1400bd013  mov     rdx, r12
0x1400bd016  mov     r15, [rsp+1A8h+Object]
0x1400bd01b  mov     rcx, r15
0x1400bd01e  call    cs:__imp_RtlGetNonVolatileToken
0x1400bd025  nop     dword ptr [rax+rax+00h]
0x1400bd02a  mov     edi, eax
0x1400bd02c  mov     [rsp+1A8h+var_158], eax
0x1400bd030  jmp     short loc_1400BD07B
0x1400bd032  mov     edi, eax
0x1400bd034  mov     [rsp+1A8h+var_158], eax
0x1400bd038  xor     ebx, ebx
0x1400bd03a  mov     r15, [rsp+1A8h+Object]
0x1400bd03f  mov     rax, [rsp+1A8h+var_118]
0x1400bd047  mov     [rsp+1A8h+var_120], rax
0x1400bd04f  mov     rsi, [rsp+1A8h+var_110]
0x1400bd057  mov     r13, [rsp+1A8h+var_108]
0x1400bd05f  mov     [rsp+1A8h+var_160], rsi
0x1400bd064  mov     r14, [rsp+1A8h+var_F8]
0x1400bd06c  mov     rax, [rsp+1A8h+var_148]
0x1400bd071  mov     [rsp+1A8h+var_130], rax
0x1400bd076  mov     r12, [rsp+1A8h+var_140]
0x1400bd07b  mov     rcx, r15
0x1400bd07e  call    VsmmDaxFilepUnmapSystemVa
0x1400bd083  test    edi, edi
0x1400bd085  jns     loc_1400BD174
0x1400bd08b  mov     eax, cs:dword_140065110
0x1400bd091  cmp     eax, 2
0x1400bd094  jbe     loc_1400BD1B8
0x1400bd09a  mov     edx, 100h
0x1400bd09f  lea     rcx, dword_140065110
0x1400bd0a6  call    _tlgKeywordOn
0x1400bd0ab  test    al, al
0x1400bd0ad  jz      loc_1400BD1B8
0x1400bd0b3  lea     rdx, aVsmmdaxfileplo; "VsmmDaxFilepLockContextSetup"
0x1400bd0ba  lea     rcx, [rsp+1A8h+var_98]
0x1400bd0c2  call    _tlgCreate1Sz_char
0x1400bd0c7  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bd0ce  lea     rcx, [rsp+1A8h+var_88]
0x1400bd0d6  call    _tlgCreate1Sz_char
0x1400bd0db  mov     dword ptr [rsp+1A8h+var_160], 798h
0x1400bd0e3  lea     rax, [rsp+1A8h+var_160]
0x1400bd0e8  mov     [rsp+1A8h+var_78], rax
0x1400bd0f0  mov     [rsp+1A8h+var_70], 4
0x1400bd0fc  mov     rax, [rsp+1A8h+var_130]
0x1400bd101  mov     [rsp+1A8h+var_140], rax
0x1400bd106  lea     rax, [rsp+1A8h+var_140]
0x1400bd10b  mov     [rsp+1A8h+var_68], rax
0x1400bd113  mov     [rsp+1A8h+var_60], 8
0x1400bd11f  mov     [rsp+1A8h+var_148], r12
0x1400bd124  lea     rax, [rsp+1A8h+var_148]
0x1400bd129  mov     [rsp+1A8h+var_58], rax
0x1400bd131  mov     [rsp+1A8h+var_50], 8
0x1400bd13d  lea     rax, [rsp+1A8h+var_B8]
0x1400bd145  mov     qword ptr [rsp+1A8h+AllocationAttributes], rax
0x1400bd14a  mov     [rsp+1A8h+SectionPageProtection], 7
0x1400bd152  xor     r9d, r9d
0x1400bd155  xor     r8d, r8d
0x1400bd158  lea     rdx, qword_140050978
0x1400bd15f  lea     rcx, dword_140065110
0x1400bd166  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400bd16b  jmp     short loc_1400BD1B8
0x1400bd16d  inc     eax
0x1400bd16f  jmp     loc_1400BCFA0
0x1400bd174  mov     r15, [rsp+1A8h+arg_18]
0x1400bd17c  mov     rax, [rsp+1A8h+var_128]
0x1400bd184  mov     rcx, [rsp+1A8h+var_138]
0x1400bd189  mov     [rcx+18h], rax
0x1400bd18d  mov     rax, [rsp+1A8h+var_160]
0x1400bd192  mov     rcx, [rsp+1A8h+arg_8]
0x1400bd19a  mov     [rax], rcx
0x1400bd19d  mov     [rsi+10h], r15
0x1400bd1a1  mov     [rsi+18h], r13
0x1400bd1a5  lea     rax, VsmmMemoryBlockpAssignPagesFromDaxFileRange
0x1400bd1ac  mov     [rsi+20h], rax
0x1400bd1b0  mov     al, [r14]
0x1400bd1b3  mov     [rsi+28h], al
0x1400bd1b6  mov     edi, ebx
0x1400bd1b8  mov     rcx, [rsp+1A8h+SectionHandle]; Handle
0x1400bd1bd  test    rcx, rcx
0x1400bd1c0  jz      short loc_1400BD1CE
0x1400bd1c2  call    cs:__imp_ZwClose
0x1400bd1c9  nop     dword ptr [rax+rax+00h]
0x1400bd1ce  test    edi, edi
0x1400bd1d0  jns     loc_1400BD2CB
0x1400bd1d6  mov     rcx, rsi
0x1400bd1d9  call    VsmmDaxFilepLockContextTeardown
0x1400bd1de  test    edi, edi
0x1400bd1e0  jns     loc_1400BD2CB
0x1400bd1e6  mov     eax, cs:dword_140065110
0x1400bd1ec  cmp     eax, 2
0x1400bd1ef  jbe     loc_1400BD2CB
0x1400bd1f5  mov     edx, 100h
0x1400bd1fa  lea     rcx, dword_140065110
0x1400bd201  call    _tlgKeywordOn
0x1400bd206  test    al, al
0x1400bd208  jz      loc_1400BD2CB
0x1400bd20e  lea     rdx, aVsmmdaxfileplo; "VsmmDaxFilepLockContextSetup"
0x1400bd215  lea     rcx, [rsp+1A8h+var_98]
0x1400bd21d  call    _tlgCreate1Sz_char
0x1400bd222  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bd229  lea     rcx, [rsp+1A8h+var_88]
0x1400bd231  call    _tlgCreate1Sz_char
0x1400bd236  mov     dword ptr [rsp+1A8h+var_160], 7B7h
0x1400bd23e  lea     rax, [rsp+1A8h+var_160]
0x1400bd243  mov     [rsp+1A8h+var_78], rax
0x1400bd24b  mov     [rsp+1A8h+var_70], 4
0x1400bd257  mov     dword ptr [rsp+1A8h+Object], edi
0x1400bd25b  lea     rax, [rsp+1A8h+Object]
0x1400bd260  mov     [rsp+1A8h+var_68], rax
0x1400bd268  mov     [rsp+1A8h+var_60], 4
0x1400bd274  mov     rax, [rsp+1A8h+var_120]
0x1400bd27c  mov     rax, [rax]
0x1400bd27f  mov     [rsp+1A8h+var_138], rax
0x1400bd284  lea     rax, [rsp+1A8h+var_138]
0x1400bd289  mov     [rsp+1A8h+var_58], rax
0x1400bd291  mov     [rsp+1A8h+var_50], 8
0x1400bd29d  lea     rax, [rsp+1A8h+var_B8]
0x1400bd2a5  mov     qword ptr [rsp+1A8h+AllocationAttributes], rax
0x1400bd2aa  mov     [rsp+1A8h+SectionPageProtection], 7
0x1400bd2b2  xor     r9d, r9d
0x1400bd2b5  xor     r8d, r8d
0x1400bd2b8  lea     rdx, byte_1400509CB
0x1400bd2bf  lea     rcx, dword_140065110
0x1400bd2c6  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400bd2cb  mov     eax, edi
0x1400bd2cd  mov     rcx, [rsp+1A8h+var_48]
0x1400bd2d5  xor     rcx, rsp; StackCookie
0x1400bd2d8  call    __security_check_cookie
0x1400bd2dd  add     rsp, 170h
0x1400bd2e4  pop     r15
0x1400bd2e6  pop     r14
0x1400bd2e8  pop     r13
0x1400bd2ea  pop     r12
0x1400bd2ec  pop     rdi
0x1400bd2ed  pop     rsi
0x1400bd2ee  pop     rbx
0x1400bd2ef  retn
```
