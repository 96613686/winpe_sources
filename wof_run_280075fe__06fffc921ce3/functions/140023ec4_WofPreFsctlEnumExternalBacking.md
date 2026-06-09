# WofPreFsctlEnumExternalBacking

- ea: `0x140023ec4`
- end: `0x14002406f`
- name: `WofPreFsctlEnumExternalBacking`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x1400346f0`

## callees

- `0x1400014d0`
- `0x14000bcbc`
- `0x14000f3d4`
- `0x140011560`
- `0x140023ec4`
- `0x140032cd8`

## import_xrefs

- `FLTMGR!FltReleaseContext` at `0x140023f2b`
- `FLTMGR!FltReleaseContext` at `0x140023f3f`
- `FLTMGR!FltReleaseContext` at `0x140023f2b`
- `FLTMGR!FltReleaseContext` at `0x140023f3f`
- `FLTMGR!FltQueryDirectoryFile` at `0x140024016`
- `FLTMGR!FltQueryDirectoryFile` at `0x140024016`

## pseudocode

```c
__int64 __fastcall WofPreFsctlEnumExternalBacking(__int64 a1, __int64 a2, _QWORD *a3)
{
  void *v3; // rsi
  __int64 v4; // rax
  bool v7; // cf
  int HandleContext; // eax
  unsigned int v9; // ebx
  __int64 v11; // rdi
  BOOLEAN RestartScan; // cl
  _OWORD *v13; // rcx
  ULONG LengthReturned; // [rsp+50h] [rbp-30h] BYREF
  void *v15; // [rsp+58h] [rbp-28h] BYREF
  __int64 v16; // [rsp+60h] [rbp-20h]
  __int128 FileInformation; // [rsp+68h] [rbp-18h] BYREF

  v3 = 0;
  *a3 = 0;
  v4 = *(_QWORD *)(a1 + 16);
  FileInformation = 0;
  LengthReturned = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v7 = *(_DWORD *)(v4 + 24) < 0x10u;
  v15 = 0;
  v16 = 0;
  if ( v7 )
  {
    HandleContext = -1073741789;
  }
  else if ( (unsigned __int8)WofUserIsAdmin() )
  {
    HandleContext = WofFindOrCreateHandleContext(
                      *(PFLT_INSTANCE *)(*(_QWORD *)(a1 + 16) + 16LL),
                      *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 8LL));
    v11 = v16;
    if ( HandleContext >= 0 )
    {
      RestartScan = 0;
      if ( *(_QWORD *)(v16 + 40) )
        goto LABEL_15;
      HandleContext = WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &v15);
      v3 = v15;
      if ( HandleContext >= 0 )
      {
        HandleContext = WofOpenReparseIndex(
                          (__int64)v15,
                          *(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL),
                          (PFILE_OBJECT *)(v11 + 48),
                          (void **)(v11 + 40));
        if ( HandleContext >= 0 )
        {
          RestartScan = 1;
LABEL_15:
          while ( 1 )
          {
            HandleContext = FltQueryDirectoryFile(
                              *(PFLT_INSTANCE *)(a2 + 24),
                              *(PFILE_OBJECT *)(v11 + 48),
                              &FileInformation,
                              0x10u,
                              FileReparsePointInformation,
                              1u,
                              0,
                              RestartScan,
                              &LengthReturned);
            if ( HandleContext < 0 )
              break;
            RestartScan = 0;
            if ( DWORD2(FileInformation) == FileTag )
            {
              v13 = *(_OWORD **)(*(_QWORD *)(a1 + 16) + 48LL);
              *v13 = 0;
              *(_QWORD *)v13 = FileInformation;
              *(_DWORD *)(a1 + 24) = 0;
              *(_QWORD *)(a1 + 32) = 16;
              goto LABEL_4;
            }
          }
        }
      }
    }
    if ( HandleContext == -2147483642 )
    {
      v9 = 0;
      goto LABEL_5;
    }
  }
  else
  {
    HandleContext = -1073741790;
  }
  *(_DWORD *)(a1 + 24) = HandleContext;
LABEL_4:
  v9 = 4;
LABEL_5:
  if ( v3 )
    FltReleaseContext(v3);
  return v9;
}

```

## disassembly

```asm
0x140023ec4  mov     [rsp-28h+arg_18], rbx
0x140023ec9  push    rbp
0x140023eca  push    rsi
0x140023ecb  push    rdi
0x140023ecc  push    r14
0x140023ece  push    r15
0x140023ed0  mov     rbp, rsp
0x140023ed3  sub     rsp, 80h
0x140023eda  mov     rax, cs:__security_cookie
0x140023ee1  xor     rax, rsp
0x140023ee4  mov     [rbp+var_8], rax
0x140023ee8  xor     esi, esi
0x140023eea  xor     edi, edi
0x140023eec  mov     [r8], rsi
0x140023eef  xorps   xmm0, xmm0
0x140023ef2  mov     rax, [rcx+10h]
0x140023ef6  mov     r15, rdx
0x140023ef9  movups  [rbp+FileInformation], xmm0
0x140023efd  mov     [rbp+var_30], esi
0x140023f00  mov     r14, rcx
0x140023f03  mov     [rcx+20h], rsi
0x140023f07  cmp     dword ptr [rax+18h], 10h
0x140023f0b  mov     [rbp+var_28], rsi
0x140023f0f  mov     [rbp+var_20], rdi
0x140023f13  jnb     short loc_140023F71
0x140023f15  mov     eax, 0C0000023h
0x140023f1a  mov     [r14+18h], eax
0x140023f1e  mov     ebx, 4
0x140023f23  test    rdi, rdi
0x140023f26  jz      short loc_140023F37
0x140023f28  mov     rcx, rdi; Context
0x140023f2b  call    cs:__imp_FltReleaseContext
0x140023f32  nop     dword ptr [rax+rax+00h]
0x140023f37  test    rsi, rsi
0x140023f3a  jz      short loc_140023F4B
0x140023f3c  mov     rcx, rsi; Context
0x140023f3f  call    cs:__imp_FltReleaseContext
0x140023f46  nop     dword ptr [rax+rax+00h]
0x140023f4b  mov     eax, ebx
0x140023f4d  mov     rcx, [rbp+var_8]
0x140023f51  xor     rcx, rsp; StackCookie
0x140023f54  call    __security_check_cookie
0x140023f59  mov     rbx, [rsp+80h+arg_18]
0x140023f61  add     rsp, 80h
0x140023f68  pop     r15
0x140023f6a  pop     r14
0x140023f6c  pop     rdi
0x140023f6d  pop     rsi
0x140023f6e  pop     rbp
0x140023f6f  retn
0x140023f71  call    WofUserIsAdmin
0x140023f76  test    al, al
0x140023f78  jnz     short loc_140023F81
0x140023f7a  mov     eax, 0C0000022h
0x140023f7f  jmp     short loc_140023F1A
0x140023f81  mov     rcx, [r14+10h]
0x140023f85  lea     r9, [rbp+var_20]
0x140023f89  mov     rdx, [rcx+8]; FileObject
0x140023f8d  mov     rcx, [rcx+10h]; Instance
0x140023f91  call    WofFindOrCreateHandleContext
0x140023f96  mov     rdi, [rbp+var_20]
0x140023f9a  test    eax, eax
0x140023f9c  js      loc_14002405D
0x140023fa2  xor     cl, cl
0x140023fa4  cmp     [rdi+28h], rsi
0x140023fa8  jnz     short loc_140023FE1
0x140023faa  mov     rcx, [r15+18h]; Instance
0x140023fae  lea     rdx, [rbp+var_28]
0x140023fb2  call    WofGetVolumeContext
0x140023fb7  mov     rsi, [rbp+var_28]
0x140023fbb  test    eax, eax
0x140023fbd  js      loc_14002405D
0x140023fc3  mov     rdx, [r14+10h]
0x140023fc7  lea     r8, [rdi+30h]
0x140023fcb  lea     r9, [rdi+28h]
0x140023fcf  mov     rcx, rsi
0x140023fd2  mov     rdx, [rdx+8]
0x140023fd6  call    WofOpenReparseIndex
0x140023fdb  test    eax, eax
0x140023fdd  js      short loc_14002405D
0x140023fdf  mov     cl, 1
0x140023fe1  mov     rdx, [rdi+30h]; FileObject
0x140023fe5  lea     rax, [rbp+var_30]
0x140023fe9  mov     [rsp+80h+LengthReturned], rax; LengthReturned
0x140023fee  lea     r8, [rbp+FileInformation]; FileInformation
0x140023ff2  mov     [rsp+80h+RestartScan], cl; RestartScan
0x140023ff6  mov     r9d, 10h; Length
0x140023ffc  mov     rcx, [r15+18h]; Instance
0x140024000  mov     [rsp+80h+FileName], 0; FileName
0x140024009  mov     [rsp+80h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14002400e  mov     [rsp+80h+FileInformationClass], 21h ; '!'; FileInformationClass
0x140024016  call    cs:__imp_FltQueryDirectoryFile
0x14002401d  nop     dword ptr [rax+rax+00h]
0x140024022  test    eax, eax
0x140024024  js      short loc_14002405D
0x140024026  mov     eax, cs:FileTag
0x14002402c  xor     cl, cl
0x14002402e  cmp     dword ptr [rbp+FileInformation+8], eax
0x140024031  jnz     short loc_140023FE1
0x140024033  mov     rax, [r14+10h]
0x140024037  xorps   xmm0, xmm0
0x14002403a  mov     rcx, [rax+30h]
0x14002403e  movups  xmmword ptr [rcx], xmm0
0x140024041  mov     rax, qword ptr [rbp+FileInformation]
0x140024045  mov     [rcx], rax
0x140024048  mov     dword ptr [r14+18h], 0
0x140024050  mov     qword ptr [r14+20h], 10h
0x140024058  jmp     loc_140023F1E
0x14002405d  cmp     eax, 80000006h
0x140024062  jnz     loc_140023F1A
0x140024068  xor     ebx, ebx
0x14002406a  jmp     loc_140023F23
```
