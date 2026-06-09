# SxGetVolumeDescription(ushort const *,CBsString *)

- ea: `0x180029ce0`
- end: `0x18002a084`
- name: `?SxGetVolumeDescription@@YAJPEBGPEAVCBsString@@@Z`
- size: `932`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CBsString *this)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e7b0`
- `0x18001e508`

## callees

- `0x18000f8ac`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x180029ce0`
- `0x18002d6e8`
- `0x18002d778`
- `0x180034de0`
- `0x180034f3c`
- `0x18003532c`
- `0x180035464`
- `0x180035b9a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180029e34`
- `KERNEL32!GetLastError` at `0x180029eec`
- `KERNEL32!GetLastError` at `0x180029e34`
- `KERNEL32!GetLastError` at `0x180029eec`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180029ee2`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180029ee2`
- `KERNEL32!GetVolumeInformationW` at `0x180029e2a`
- `KERNEL32!GetVolumeInformationW` at `0x180029e2a`
- `ntdll!RtlSetThreadErrorMode` at `0x180029d7c`
- `ntdll!RtlSetThreadErrorMode` at `0x18002a055`
- `ntdll!RtlSetThreadErrorMode` at `0x180029d7c`
- `ntdll!RtlSetThreadErrorMode` at `0x18002a055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a04a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029dc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a041`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a04a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029dd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029eb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029dd6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180029eb6`

## pseudocode

```c
__int64 __fastcall SxGetVolumeDescription(const unsigned __int16 *a1, struct CBsString *this)
{
  unsigned __int16 *v4; // r14
  _WORD *v5; // rsi
  unsigned int v6; // eax
  __int16 v7; // ax
  __int64 v8; // rdi
  DWORD LastError; // eax
  __int64 v10; // rcx
  DWORD v11; // ecx
  __int16 v12; // r15
  DWORD v13; // edi
  __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int16 *i; // rdi
  unsigned __int16 v17; // dx
  __int64 v18; // rax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  __int64 v21; // r8
  DWORD MaximumComponentLength; // [rsp+40h] [rbp-40h] BYREF
  int LastFailureAsHRESULT; // [rsp+48h] [rbp-38h] BYREF
  __int16 v25; // [rsp+4Ch] [rbp-34h]
  __int16 v26; // [rsp+4Eh] [rbp-32h]
  int v27; // [rsp+50h] [rbp-30h]
  DWORD cchReturnLength; // [rsp+C8h] [rbp+48h] BYREF
  ULONG OldMode; // [rsp+D0h] [rbp+50h] BYREF
  DWORD FileSystemFlags; // [rsp+D8h] [rbp+58h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, "SxGetVolumeDescription", 572, 1);
  cchReturnLength = 0;
  v4 = 0;
  FileSystemFlags = 0;
  v5 = 0;
  MaximumComponentLength = 0;
  OldMode = 0;
  if ( this )
    CBsString::Empty(this);
  v6 = RtlSetThreadErrorMode(0x10u, &OldMode);
  LastFailureAsHRESULT = HRESULTFromNTSTATUS(v6);
  v7 = 588;
  if ( LastFailureAsHRESULT >= 0 )
  {
    v25 = 588;
    v7 = 590;
    if ( this )
    {
      LODWORD(v8) = 32;
      while ( 1 )
      {
        v25 = v7;
        LastFailureAsHRESULT = 0;
        v8 = SxScaledGrowth(v8);
        CoTaskMemFree(v5);
        v5 = CoTaskMemAlloc((unsigned int)(2 * v8 + 2));
        v7 = 599;
        if ( !v5 )
          break;
        LastFailureAsHRESULT = 0;
        v25 = 599;
        memset_0(v5, 0, (unsigned int)(2 * v8 + 2));
        if ( GetVolumeInformationW(a1, v5, v8, 0, &MaximumComponentLength, &FileSystemFlags, 0, 0)
          || (LastError = GetLastError(), LastError == 21) )
        {
          v5[v8] = 0;
          if ( *v5 )
          {
            LastFailureAsHRESULT = CBsString::Append(this, v5);
            v7 = 620;
            if ( LastFailureAsHRESULT < 0 )
              goto LABEL_48;
            v25 = 620;
          }
          v11 = 64;
          v12 = 636;
          cchReturnLength = 64;
          while ( 1 )
          {
            v13 = SxScaledGrowth(v11);
            CoTaskMemFree(v4);
            v4 = (unsigned __int16 *)CoTaskMemAlloc(2LL * v13);
            v7 = 630;
            if ( !v4 )
              goto LABEL_46;
            LastFailureAsHRESULT = 0;
            v25 = 630;
            if ( GetVolumePathNamesForVolumeNameW(a1, v4, v13, &cchReturnLength) )
            {
              v15 = -1;
              do
                ++v15;
              while ( v4[v15] );
              if ( v15 )
              {
                if ( *v5 )
                {
                  LastFailureAsHRESULT = CBsString::Append(this, L" ");
                  v7 = 652;
                  if ( LastFailureAsHRESULT < 0 )
                    goto LABEL_48;
                  v25 = 652;
                }
                LastFailureAsHRESULT = CBsString::Append(this, L"(");
                v7 = 654;
                if ( LastFailureAsHRESULT < 0 )
                  goto LABEL_48;
                v25 = 654;
                v12 = 660;
                for ( i = v4; *i; i += v18 + 1 )
                {
                  if ( i != v4 )
                  {
                    LastFailureAsHRESULT = CBsString::Append(this, L", ");
                    if ( LastFailureAsHRESULT < 0 )
                      goto LABEL_24;
                    v25 = 660;
                  }
                  LastFailureAsHRESULT = CBsString::Append(this, i);
                  v7 = 662;
                  if ( LastFailureAsHRESULT < 0 )
                    goto LABEL_48;
                  v25 = 662;
                  CBsString::UnTrailing(this, v17);
                  v18 = -1;
                  do
                    ++v18;
                  while ( i[v18] );
                }
                LastFailureAsHRESULT = CBsString::Append(this, L")");
                v7 = 665;
                if ( LastFailureAsHRESULT < 0 )
                  goto LABEL_48;
                v25 = 665;
              }
              if ( *((_DWORD *)this + 2) )
                goto LABEL_49;
              LastFailureAsHRESULT = CBsString::Set(this, a1);
              v7 = 670;
              if ( LastFailureAsHRESULT >= 0 )
              {
                v25 = 670;
                goto LABEL_49;
              }
              goto LABEL_48;
            }
            if ( GetLastError() != 234 )
            {
              LastFailureAsHRESULT = GetLastFailureAsHRESULT(v14);
LABEL_24:
              v26 = v12;
              goto LABEL_49;
            }
            v11 = cchReturnLength;
            LastFailureAsHRESULT = 0;
            v25 = 636;
          }
        }
        if ( LastError != 234 )
        {
          LastFailureAsHRESULT = GetLastFailureAsHRESULT(v10);
          v7 = 614;
          v27 = 1;
          goto LABEL_48;
        }
        v7 = 614;
      }
LABEL_46:
      LastFailureAsHRESULT = -2147024882;
    }
    else
    {
      LastFailureAsHRESULT = -2147024809;
    }
  }
LABEL_48:
  v26 = v7;
LABEL_49:
  CoTaskMemFree(v4);
  CoTaskMemFree(v5);
  RtlSetThreadErrorMode(OldMode, 0);
  v19 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT, v20, v21);
  return v19;
}

```

## disassembly

```asm
0x180029ce0  mov     [rsp-38h+arg_0], rbx
0x180029ce5  push    rbp
0x180029ce6  push    rsi
0x180029ce7  push    rdi
0x180029ce8  push    r12
0x180029cea  push    r13
0x180029cec  push    r14
0x180029cee  push    r15
0x180029cf0  mov     rbp, rsp
0x180029cf3  sub     rsp, 80h
0x180029cfa  mov     rbx, rdx
0x180029cfd  mov     r12, rcx
0x180029d00  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d07  lea     rax, WPP_GLOBAL_Control
0x180029d0e  cmp     rcx, rax
0x180029d11  jz      short loc_180029D31
0x180029d13  test    dword ptr [rcx+1Ch], 20000000h
0x180029d1a  jz      short loc_180029D31
0x180029d1c  mov     rcx, [rcx+10h]
0x180029d20  lea     r8, WPP_05ac73db944e38c734cd0ea2eac4b7ce_Traceguids
0x180029d27  mov     edx, 16h
0x180029d2c  call    WPP_SF_
0x180029d31  mov     r9d, 1; unsigned __int16
0x180029d37  lea     rdx, aSxgetvolumedes; "SxGetVolumeDescription"
0x180029d3e  mov     r8d, 23Ch; unsigned __int16
0x180029d44  lea     rcx, [rbp+var_38]; this
0x180029d48  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180029d4d  xor     r13d, r13d
0x180029d50  mov     [rbp+cchReturnLength], r13d
0x180029d54  mov     r14d, r13d
0x180029d57  mov     [rbp+FileSystemFlags], r13d
0x180029d5b  mov     esi, r13d
0x180029d5e  mov     [rbp+MaximumComponentLength], r13d
0x180029d62  mov     [rbp+OldMode], r13d
0x180029d66  test    rbx, rbx
0x180029d69  jz      short loc_180029D73
0x180029d6b  mov     rcx, rbx; this
0x180029d6e  call    ?Empty@CBsString@@QEAAXXZ; CBsString::Empty(void)
0x180029d73  lea     rdx, [rbp+OldMode]; OldMode
0x180029d77  mov     ecx, 10h; NewMode
0x180029d7c  call    cs:__imp_RtlSetThreadErrorMode
0x180029d82  mov     ecx, eax
0x180029d84  call    HRESULTFromNTSTATUS
0x180029d89  mov     [rbp+var_38], eax
0x180029d8c  test    eax, eax
0x180029d8e  mov     eax, 24Ch
0x180029d93  js      loc_18002A03A
0x180029d99  mov     [rbp+var_34], ax
0x180029d9d  mov     eax, 24Eh
0x180029da2  test    rbx, rbx
0x180029da5  jz      loc_18002A033
0x180029dab  mov     edi, 20h ; ' '
0x180029db0  mov     ecx, edi; unsigned int
0x180029db2  mov     [rbp+var_34], ax
0x180029db6  mov     [rbp+var_38], r13d
0x180029dba  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180029dbf  mov     rcx, rsi; pv
0x180029dc2  mov     edi, eax
0x180029dc4  call    cs:__imp_CoTaskMemFree
0x180029dca  lea     eax, ds:2[rdi*2]
0x180029dd1  mov     ecx, eax; cb
0x180029dd3  mov     r15d, eax
0x180029dd6  call    cs:__imp_CoTaskMemAlloc
0x180029ddc  mov     rsi, rax
0x180029ddf  test    rax, rax
0x180029de2  mov     eax, 257h
0x180029de7  jz      loc_18002A02A
0x180029ded  mov     r8d, r15d; Size
0x180029df0  mov     [rbp+var_38], r13d
0x180029df4  xor     edx, edx; Val
0x180029df6  mov     [rbp+var_34], ax
0x180029dfa  mov     rcx, rsi; void *
0x180029dfd  call    memset_0
0x180029e02  mov     [rsp+80h+nFileSystemNameSize], r13d; nFileSystemNameSize
0x180029e07  lea     rax, [rbp+FileSystemFlags]
0x180029e0b  mov     [rsp+80h+lpFileSystemNameBuffer], r13; lpFileSystemNameBuffer
0x180029e10  xor     r9d, r9d; lpVolumeSerialNumber
0x180029e13  mov     [rsp+80h+lpFileSystemFlags], rax; lpFileSystemFlags
0x180029e18  mov     r8d, edi; nVolumeNameSize
0x180029e1b  lea     rax, [rbp+MaximumComponentLength]
0x180029e1f  mov     rdx, rsi; lpVolumeNameBuffer
0x180029e22  mov     rcx, r12; lpRootPathName
0x180029e25  mov     [rsp+80h+lpMaximumComponentLength], rax; lpMaximumComponentLength
0x180029e2a  call    cs:__imp_GetVolumeInformationW
0x180029e30  test    eax, eax
0x180029e32  jnz     short loc_180029E69
0x180029e34  call    cs:__imp_GetLastError
0x180029e3a  cmp     eax, 15h
0x180029e3d  jz      short loc_180029E69
0x180029e3f  cmp     eax, 0EAh
0x180029e44  jnz     short loc_180029E50
0x180029e46  mov     eax, 266h
0x180029e4b  jmp     loc_180029DB0
0x180029e50  call    GetLastFailureAsHRESULT
0x180029e55  mov     [rbp+var_38], eax
0x180029e58  mov     eax, 266h
0x180029e5d  mov     [rbp+var_30], 1
0x180029e64  jmp     loc_18002A03A
0x180029e69  mov     [rsi+rdi*2], r13w
0x180029e6e  cmp     [rsi], r13w
0x180029e72  jz      short loc_180029E93
0x180029e74  mov     rdx, rsi; unsigned __int16 *
0x180029e77  mov     rcx, rbx; this
0x180029e7a  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180029e7f  mov     [rbp+var_38], eax
0x180029e82  test    eax, eax
0x180029e84  mov     eax, 26Ch
0x180029e89  js      loc_18002A03A
0x180029e8f  mov     [rbp+var_34], ax
0x180029e93  mov     ecx, 40h ; '@'; unsigned int
0x180029e98  mov     r15d, 27Ch
0x180029e9e  mov     [rbp+cchReturnLength], ecx
0x180029ea1  call    ?SxScaledGrowth@@YAKK@Z; SxScaledGrowth(ulong)
0x180029ea6  mov     rcx, r14; pv
0x180029ea9  mov     edi, eax
0x180029eab  call    cs:__imp_CoTaskMemFree
0x180029eb1  mov     ecx, edi
0x180029eb3  add     rcx, rcx; cb
0x180029eb6  call    cs:__imp_CoTaskMemAlloc
0x180029ebc  mov     r14, rax
0x180029ebf  test    rax, rax
0x180029ec2  mov     eax, 276h
0x180029ec7  jz      loc_18002A02A
0x180029ecd  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x180029ed1  mov     [rbp+var_38], r13d
0x180029ed5  mov     r8d, edi; cchBufferLength
0x180029ed8  mov     [rbp+var_34], ax
0x180029edc  mov     rdx, r14; lpszVolumePathNames
0x180029edf  mov     rcx, r12; lpszVolumeName
0x180029ee2  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180029ee8  test    eax, eax
0x180029eea  jnz     short loc_180029F19
0x180029eec  call    cs:__imp_GetLastError
0x180029ef2  cmp     eax, 0EAh
0x180029ef7  jnz     short loc_180029F07
0x180029ef9  mov     ecx, [rbp+cchReturnLength]
0x180029efc  mov     [rbp+var_38], r13d
0x180029f00  mov     [rbp+var_34], r15w
0x180029f05  jmp     short loc_180029EA1
0x180029f07  call    GetLastFailureAsHRESULT
0x180029f0c  mov     [rbp+var_38], eax
0x180029f0f  mov     [rbp+var_32], r15w
0x180029f14  jmp     loc_18002A03E
0x180029f19  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029f1d  inc     rax
0x180029f20  cmp     [r14+rax*2], r13w
0x180029f25  jnz     short loc_180029F1D
0x180029f27  test    rax, rax
0x180029f2a  jz      loc_18002A007
0x180029f30  cmp     [rsi], r13w
0x180029f34  jz      short loc_180029F59
0x180029f36  lea     rdx, asc_18003A418; " "
0x180029f3d  mov     rcx, rbx; this
0x180029f40  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180029f45  mov     [rbp+var_38], eax
0x180029f48  test    eax, eax
0x180029f4a  mov     eax, 28Ch
0x180029f4f  js      loc_18002A03A
0x180029f55  mov     [rbp+var_34], ax
0x180029f59  lea     rdx, asc_18003CBB0; "("
0x180029f60  mov     rcx, rbx; this
0x180029f63  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180029f68  mov     [rbp+var_38], eax
0x180029f6b  test    eax, eax
0x180029f6d  mov     eax, 28Eh
0x180029f72  js      loc_18002A03A
0x180029f78  mov     [rbp+var_34], ax
0x180029f7c  lea     r15d, [rax+6]
0x180029f80  mov     rdi, r14
0x180029f83  cmp     [rdi], r13w
0x180029f87  jz      short loc_180029FE8
0x180029f89  cmp     rdi, r14
0x180029f8c  jz      short loc_180029FAD
0x180029f8e  lea     rdx, asc_18003CBB4; ", "
0x180029f95  mov     rcx, rbx; this
0x180029f98  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180029f9d  mov     [rbp+var_38], eax
0x180029fa0  test    eax, eax
0x180029fa2  js      loc_180029F0F
0x180029fa8  mov     [rbp+var_34], r15w
0x180029fad  mov     rdx, rdi; unsigned __int16 *
0x180029fb0  mov     rcx, rbx; this
0x180029fb3  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180029fb8  mov     [rbp+var_38], eax
0x180029fbb  test    eax, eax
0x180029fbd  mov     eax, 296h
0x180029fc2  js      short loc_18002A03A
0x180029fc4  mov     rcx, rbx; this
0x180029fc7  mov     [rbp+var_34], ax
0x180029fcb  call    ?UnTrailing@CBsString@@QEAAXG@Z; CBsString::UnTrailing(ushort)
0x180029fd0  or      rax, 0FFFFFFFFFFFFFFFFh
0x180029fd4  inc     rax
0x180029fd7  cmp     [rdi+rax*2], r13w
0x180029fdc  jnz     short loc_180029FD4
0x180029fde  lea     rdi, [rdi+rax*2]
0x180029fe2  add     rdi, 2
0x180029fe6  jmp     short loc_180029F83
0x180029fe8  lea     rdx, asc_18003CBBC; ")"
0x180029fef  mov     rcx, rbx; this
0x180029ff2  call    ?Append@CBsString@@QEAAJPEBG@Z; CBsString::Append(ushort const *)
0x180029ff7  mov     [rbp+var_38], eax
0x180029ffa  test    eax, eax
0x180029ffc  mov     eax, 299h
0x18002a001  js      short loc_18002A03A
0x18002a003  mov     [rbp+var_34], ax
0x18002a007  cmp     [rbx+8], r13d
0x18002a00b  jnz     short loc_18002A03E
0x18002a00d  mov     rdx, r12; unsigned __int16 *
0x18002a010  mov     rcx, rbx; this
0x18002a013  call    ?Set@CBsString@@QEAAJPEBG@Z; CBsString::Set(ushort const *)
0x18002a018  mov     [rbp+var_38], eax
0x18002a01b  test    eax, eax
0x18002a01d  mov     eax, 29Eh
0x18002a022  js      short loc_18002A03A
0x18002a024  mov     [rbp+var_34], ax
0x18002a028  jmp     short loc_18002A03E
0x18002a02a  mov     [rbp+var_38], 8007000Eh
0x18002a031  jmp     short loc_18002A03A
0x18002a033  mov     [rbp+var_38], 80070057h
0x18002a03a  mov     [rbp+var_32], ax
0x18002a03e  mov     rcx, r14; pv
0x18002a041  call    cs:__imp_CoTaskMemFree
0x18002a047  mov     rcx, rsi; pv
0x18002a04a  call    cs:__imp_CoTaskMemFree
0x18002a050  mov     ecx, [rbp+OldMode]; NewMode
0x18002a053  xor     edx, edx; OldMode
0x18002a055  call    cs:__imp_RtlSetThreadErrorMode
0x18002a05b  mov     ebx, [rbp+var_38]
0x18002a05e  lea     rcx, [rbp+var_38]; this
0x18002a062  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18002a067  mov     eax, ebx
0x18002a069  mov     rbx, [rsp+80h+arg_0]
0x18002a071  add     rsp, 80h
0x18002a078  pop     r15
0x18002a07a  pop     r14
0x18002a07c  pop     r13
0x18002a07e  pop     r12
0x18002a080  pop     rdi
0x18002a081  pop     rsi
0x18002a082  pop     rbp
0x18002a083  retn
```
