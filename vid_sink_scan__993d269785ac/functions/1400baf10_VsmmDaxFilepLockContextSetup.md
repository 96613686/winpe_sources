# VsmmDaxFilepLockContextSetup

- ea: `0x1400baf10`
- end: `0x1400bb3e1`
- name: `VsmmDaxFilepLockContextSetup`
- size: `1233`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400ba1d0`

## callees

- `0x1400029c0`
- `0x140006bf8`
- `0x14000a4e0`
- `0x140021650`
- `0x140038630`
- `0x1400baf10`
- `0x1400bb3e8`
- `0x1400bbfd4`
- `0x1400bc488`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bb040`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bb040`
- `ntoskrnl!ZwClose` at `0x1400bb2b2`
- `ntoskrnl!ZwClose` at `0x1400bb2b2`
- `ntoskrnl!RtlGetNonVolatileToken` at `0x1400bb10e`
- `ntoskrnl!RtlGetNonVolatileToken` at `0x1400bb10e`
- `ntoskrnl!ZwCreateSection` at `0x1400bafee`
- `ntoskrnl!ZwCreateSection` at `0x1400bafee`

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
              if ( (unsigned int)dword_140064110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
              {
                tlgCreate1Sz_char(v32, "VsmmDaxFilepLockContextSetup");
                tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
                LODWORD(v17) = 1919;
                v34 = &v17;
                v35 = 4;
                v21 = v23;
                p_Object = (PVOID *)&v21;
                v37 = 8;
                v20 = v13;
                v38 = (HANDLE **)&v20;
                v39 = 8;
                tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, byte_1400504DB, 0, 0, 7, v31);
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
      VidTraceErrorInternal0("VsmmDaxFilepLockContextSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 1867);
    }
  }
  else
  {
    VidTraceErrorInternal0("VsmmDaxFilepLockContextSetup", "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c", 1854);
  }
LABEL_19:
  if ( SectionHandle )
    ZwClose(SectionHandle);
  if ( NonVolatileToken < 0 )
  {
    VsmmDaxFilepLockContextTeardown(a1);
    if ( (unsigned int)dword_140064110 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140064110, 256) )
      {
        tlgCreate1Sz_char(v32, "VsmmDaxFilepLockContextSetup");
        tlgCreate1Sz_char(v33, "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfile.c");
        LODWORD(v17) = 1950;
        v34 = &v17;
        v35 = 4;
        LODWORD(Object) = NonVolatileToken;
        p_Object = &Object;
        v37 = 4;
        v22 = (HANDLE *)*v25;
        v38 = &v22;
        v39 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140064110, qword_140050490, 0, 0, 7, v31);
      }
    }
  }
  return (unsigned int)NonVolatileToken;
}

```

## disassembly

```asm
0x1400baf10  mov     r11, rsp
0x1400baf13  mov     [r11+20h], r9
0x1400baf17  mov     [r11+10h], rdx
0x1400baf1b  push    rbx
0x1400baf1c  push    rsi
0x1400baf1d  push    rdi
0x1400baf1e  push    r12
0x1400baf20  push    r13
0x1400baf22  push    r14
0x1400baf24  push    r15
0x1400baf26  sub     rsp, 170h
0x1400baf2d  mov     rax, cs:__security_cookie
0x1400baf34  xor     rax, rsp
0x1400baf37  mov     [rsp+1A8h+var_48], rax
0x1400baf3f  mov     r15, r9
0x1400baf42  mov     [rsp+1A8h+var_120], r8
0x1400baf4a  mov     [rsp+1A8h+var_160], rcx
0x1400baf4f  mov     [rsp+1A8h+var_118], r8
0x1400baf57  mov     rsi, rcx
0x1400baf5a  mov     [rsp+1A8h+var_110], rcx
0x1400baf62  mov     r14, r8
0x1400baf65  mov     [rsp+1A8h+var_138], r8
0x1400baf6a  mov     r13, [rsp+1A8h+arg_20]
0x1400baf72  mov     [rsp+1A8h+var_108], r13
0x1400baf7a  xor     ebx, ebx
0x1400baf7c  mov     qword ptr [r11-0F0h], 30h ; '0'
0x1400baf87  mov     qword ptr [r11-0D8h], 200h
0x1400baf92  xorps   xmm0, xmm0
0x1400baf95  movups  xmmword ptr [rcx], xmm0
0x1400baf98  movups  xmmword ptr [rcx+10h], xmm0
0x1400baf9c  movups  xmmword ptr [rcx+20h], xmm0
0x1400bafa0  mov     [r11-128h], rbx
0x1400bafa7  mov     [rsp+1A8h+SectionHandle], rbx
0x1400bafac  mov     [r11-0E8h], rbx
0x1400bafb3  mov     [r11-0E0h], rbx
0x1400bafba  movdqu  [rsp+1A8h+var_D0], xmm0
0x1400bafc3  mov     rax, [r8]
0x1400bafc6  mov     [rsp+1A8h+FileHandle], rax; FileHandle
0x1400bafcb  mov     [rsp+1A8h+AllocationAttributes], 8000000h; AllocationAttributes
0x1400bafd3  lea     r12d, [rbx+4]
0x1400bafd7  mov     [rsp+1A8h+SectionPageProtection], r12d; SectionPageProtection
0x1400bafdc  xor     r9d, r9d; MaximumSize
0x1400bafdf  lea     r8, [r11-0F0h]; ObjectAttributes
0x1400bafe6  lea     edx, [rbx+6]; DesiredAccess
0x1400bafe9  lea     rcx, [rsp+1A8h+SectionHandle]; SectionHandle
0x1400bafee  call    cs:__imp_ZwCreateSection
0x1400baff5  nop     dword ptr [rax+rax+00h]
0x1400baffa  mov     edi, eax
0x1400baffc  test    eax, eax
0x1400baffe  jns     short loc_1400BB01E
0x1400bb000  mov     r8d, 73Eh
0x1400bb006  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bb00d  lea     rcx, aVsmmdaxfileplo; "VsmmDaxFilepLockContextSetup"
0x1400bb014  call    VidTraceErrorInternal0
0x1400bb019  jmp     loc_1400BB2A8
0x1400bb01e  mov     [rsp+1A8h+Object], rbx
0x1400bb023  mov     qword ptr [rsp+1A8h+AllocationAttributes], rbx; HandleInformation
0x1400bb028  lea     rax, [rsp+1A8h+Object]
0x1400bb02d  mov     qword ptr [rsp+1A8h+SectionPageProtection], rax; Object
0x1400bb032  xor     r9d, r9d; AccessMode
0x1400bb035  xor     r8d, r8d; ObjectType
0x1400bb038  mov     edx, r12d; DesiredAccess
0x1400bb03b  mov     rcx, [rsp+1A8h+SectionHandle]; Handle
0x1400bb040  call    cs:__imp_ObReferenceObjectByHandle
0x1400bb047  nop     dword ptr [rax+rax+00h]
0x1400bb04c  mov     edi, eax
0x1400bb04e  mov     rax, [rsp+1A8h+Object]
0x1400bb053  mov     [rsi+8], rax
0x1400bb057  test    edi, edi
0x1400bb059  jns     short loc_1400BB079
0x1400bb05b  mov     r8d, 74Bh
0x1400bb061  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bb068  lea     rcx, aVsmmdaxfileplo; "VsmmDaxFilepLockContextSetup"
0x1400bb06f  call    VidTraceErrorInternal0
0x1400bb074  jmp     loc_1400BB2A8
0x1400bb079  add     r14, 20h ; ' '
0x1400bb07d  mov     [rsp+1A8h+var_F8], r14
0x1400bb085  cmp     [r14], bl
0x1400bb088  jz      loc_1400BB26C
0x1400bb08e  mov     eax, ebx
0x1400bb090  mov     ecx, eax
0x1400bb092  cmp     rcx, r15
0x1400bb095  jnb     loc_1400BB26C
0x1400bb09b  lea     rdx, [rcx+rcx*2]
0x1400bb09f  cmp     [r13+rdx*8+0], ebx
0x1400bb0a4  jnz     loc_1400BB25D
0x1400bb0aa  mov     [rsp+1A8h+Object], rbx
0x1400bb0af  mov     rcx, [r13+rdx*8+10h]
0x1400bb0b4  shl     rcx, 0Ch
0x1400bb0b8  mov     [rsp+1A8h+var_130], rcx
0x1400bb0bd  mov     [rsp+1A8h+var_148], rcx
0x1400bb0c2  mov     rax, [r13+rdx*8+8]
0x1400bb0c7  mov     r12d, 10h
0x1400bb0cd  cmp     rax, r12
0x1400bb0d0  cmovb   r12, rax
0x1400bb0d4  shl     r12, 0Ch
0x1400bb0d8  mov     [rsp+1A8h+var_140], r12
0x1400bb0dd  lea     r9, [rsp+1A8h+Object]
0x1400bb0e2  mov     r8, r12
0x1400bb0e5  mov     rdx, rcx
0x1400bb0e8  mov     rcx, [rsi+8]
0x1400bb0ec  call    VsmmDaxFilepMapSystemVa
0x1400bb0f1  mov     edi, eax
0x1400bb0f3  test    eax, eax
0x1400bb0f5  js      loc_1400BB2A8
0x1400bb0fb  lea     r8, [rsp+1A8h+var_128]
0x1400bb103  mov     rdx, r12
0x1400bb106  mov     r15, [rsp+1A8h+Object]
0x1400bb10b  mov     rcx, r15
0x1400bb10e  call    cs:__imp_RtlGetNonVolatileToken
0x1400bb115  nop     dword ptr [rax+rax+00h]
0x1400bb11a  mov     edi, eax
0x1400bb11c  mov     [rsp+1A8h+var_158], eax
0x1400bb120  jmp     short loc_1400BB16B
0x1400bb122  mov     edi, eax
0x1400bb124  mov     [rsp+1A8h+var_158], eax
0x1400bb128  xor     ebx, ebx
0x1400bb12a  mov     r15, [rsp+1A8h+Object]
0x1400bb12f  mov     rax, [rsp+1A8h+var_118]
0x1400bb137  mov     [rsp+1A8h+var_120], rax
0x1400bb13f  mov     rsi, [rsp+1A8h+var_110]
0x1400bb147  mov     r13, [rsp+1A8h+var_108]
0x1400bb14f  mov     [rsp+1A8h+var_160], rsi
0x1400bb154  mov     r14, [rsp+1A8h+var_F8]
0x1400bb15c  mov     rax, [rsp+1A8h+var_148]
0x1400bb161  mov     [rsp+1A8h+var_130], rax
0x1400bb166  mov     r12, [rsp+1A8h+var_140]
0x1400bb16b  mov     rcx, r15
0x1400bb16e  call    VsmmDaxFilepUnmapSystemVa
0x1400bb173  test    edi, edi
0x1400bb175  jns     loc_1400BB264
0x1400bb17b  mov     eax, cs:dword_140064110
0x1400bb181  cmp     eax, 2
0x1400bb184  jbe     loc_1400BB2A8
0x1400bb18a  mov     edx, 100h
0x1400bb18f  lea     rcx, dword_140064110
0x1400bb196  call    _tlgKeywordOn
0x1400bb19b  test    al, al
0x1400bb19d  jz      loc_1400BB2A8
0x1400bb1a3  lea     rdx, aVsmmdaxfileplo; "VsmmDaxFilepLockContextSetup"
0x1400bb1aa  lea     rcx, [rsp+1A8h+var_98]
0x1400bb1b2  call    _tlgCreate1Sz_char
0x1400bb1b7  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bb1be  lea     rcx, [rsp+1A8h+var_88]
0x1400bb1c6  call    _tlgCreate1Sz_char
0x1400bb1cb  mov     dword ptr [rsp+1A8h+var_160], 77Fh
0x1400bb1d3  lea     rax, [rsp+1A8h+var_160]
0x1400bb1d8  mov     [rsp+1A8h+var_78], rax
0x1400bb1e0  mov     [rsp+1A8h+var_70], 4
0x1400bb1ec  mov     rax, [rsp+1A8h+var_130]
0x1400bb1f1  mov     [rsp+1A8h+var_140], rax
0x1400bb1f6  lea     rax, [rsp+1A8h+var_140]
0x1400bb1fb  mov     [rsp+1A8h+var_68], rax
0x1400bb203  mov     [rsp+1A8h+var_60], 8
0x1400bb20f  mov     [rsp+1A8h+var_148], r12
0x1400bb214  lea     rax, [rsp+1A8h+var_148]
0x1400bb219  mov     [rsp+1A8h+var_58], rax
0x1400bb221  mov     [rsp+1A8h+var_50], 8
0x1400bb22d  lea     rax, [rsp+1A8h+var_B8]
0x1400bb235  mov     qword ptr [rsp+1A8h+AllocationAttributes], rax
0x1400bb23a  mov     [rsp+1A8h+SectionPageProtection], 7
0x1400bb242  xor     r9d, r9d
0x1400bb245  xor     r8d, r8d
0x1400bb248  lea     rdx, byte_1400504DB
0x1400bb24f  lea     rcx, dword_140064110
0x1400bb256  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400bb25b  jmp     short loc_1400BB2A8
0x1400bb25d  inc     eax
0x1400bb25f  jmp     loc_1400BB090
0x1400bb264  mov     r15, [rsp+1A8h+arg_18]
0x1400bb26c  mov     rax, [rsp+1A8h+var_128]
0x1400bb274  mov     rcx, [rsp+1A8h+var_138]
0x1400bb279  mov     [rcx+18h], rax
0x1400bb27d  mov     rax, [rsp+1A8h+var_160]
0x1400bb282  mov     rcx, [rsp+1A8h+arg_8]
0x1400bb28a  mov     [rax], rcx
0x1400bb28d  mov     [rsi+10h], r15
0x1400bb291  mov     [rsi+18h], r13
0x1400bb295  lea     rax, VsmmMemoryBlockpAssignPagesFromDaxFileRange
0x1400bb29c  mov     [rsi+20h], rax
0x1400bb2a0  mov     al, [r14]
0x1400bb2a3  mov     [rsi+28h], al
0x1400bb2a6  mov     edi, ebx
0x1400bb2a8  mov     rcx, [rsp+1A8h+SectionHandle]; Handle
0x1400bb2ad  test    rcx, rcx
0x1400bb2b0  jz      short loc_1400BB2BE
0x1400bb2b2  call    cs:__imp_ZwClose
0x1400bb2b9  nop     dword ptr [rax+rax+00h]
0x1400bb2be  test    edi, edi
0x1400bb2c0  jns     loc_1400BB3BB
0x1400bb2c6  mov     rcx, rsi
0x1400bb2c9  call    VsmmDaxFilepLockContextTeardown
0x1400bb2ce  test    edi, edi
0x1400bb2d0  jns     loc_1400BB3BB
0x1400bb2d6  mov     eax, cs:dword_140064110
0x1400bb2dc  cmp     eax, 2
0x1400bb2df  jbe     loc_1400BB3BB
0x1400bb2e5  mov     edx, 100h
0x1400bb2ea  lea     rcx, dword_140064110
0x1400bb2f1  call    _tlgKeywordOn
0x1400bb2f6  test    al, al
0x1400bb2f8  jz      loc_1400BB3BB
0x1400bb2fe  lea     rdx, aVsmmdaxfileplo; "VsmmDaxFilepLockContextSetup"
0x1400bb305  lea     rcx, [rsp+1A8h+var_98]
0x1400bb30d  call    _tlgCreate1Sz_char
0x1400bb312  lea     rdx, aOnecoreVmVidSy_71; "onecore\\vm\\vid\\sys\\vsmm\\vsmmdaxfil"...
0x1400bb319  lea     rcx, [rsp+1A8h+var_88]
0x1400bb321  call    _tlgCreate1Sz_char
0x1400bb326  mov     dword ptr [rsp+1A8h+var_160], 79Eh
0x1400bb32e  lea     rax, [rsp+1A8h+var_160]
0x1400bb333  mov     [rsp+1A8h+var_78], rax
0x1400bb33b  mov     [rsp+1A8h+var_70], 4
0x1400bb347  mov     dword ptr [rsp+1A8h+Object], edi
0x1400bb34b  lea     rax, [rsp+1A8h+Object]
0x1400bb350  mov     [rsp+1A8h+var_68], rax
0x1400bb358  mov     [rsp+1A8h+var_60], 4
0x1400bb364  mov     rax, [rsp+1A8h+var_120]
0x1400bb36c  mov     rax, [rax]
0x1400bb36f  mov     [rsp+1A8h+var_138], rax
0x1400bb374  lea     rax, [rsp+1A8h+var_138]
0x1400bb379  mov     [rsp+1A8h+var_58], rax
0x1400bb381  mov     [rsp+1A8h+var_50], 8
0x1400bb38d  lea     rax, [rsp+1A8h+var_B8]
0x1400bb395  mov     qword ptr [rsp+1A8h+AllocationAttributes], rax
0x1400bb39a  mov     [rsp+1A8h+SectionPageProtection], 7
0x1400bb3a2  xor     r9d, r9d
0x1400bb3a5  xor     r8d, r8d
0x1400bb3a8  lea     rdx, qword_140050490
0x1400bb3af  lea     rcx, dword_140064110
0x1400bb3b6  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400bb3bb  mov     eax, edi
0x1400bb3bd  mov     rcx, [rsp+1A8h+var_48]
0x1400bb3c5  xor     rcx, rsp; StackCookie
0x1400bb3c8  call    __security_check_cookie
0x1400bb3cd  add     rsp, 170h
0x1400bb3d4  pop     r15
0x1400bb3d6  pop     r14
0x1400bb3d8  pop     r13
0x1400bb3da  pop     r12
0x1400bb3dc  pop     rdi
0x1400bb3dd  pop     rsi
0x1400bb3de  pop     rbx
0x1400bb3df  retn
```
