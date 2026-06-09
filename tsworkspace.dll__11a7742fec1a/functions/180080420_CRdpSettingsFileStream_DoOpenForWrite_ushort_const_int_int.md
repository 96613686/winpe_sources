# CRdpSettingsFileStream::DoOpenForWrite(ushort const *,int,int)

- ea: `0x180080420`
- end: `0x180080702`
- name: `?DoOpenForWrite@CRdpSettingsFileStream@@IEAAJPEBGHH@Z`
- size: `738`
- prototype: `__int64 __fastcall(CRdpSettingsFileStream *__hidden this, const unsigned __int16 *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callers

- `0x180080e80`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001c6e4`
- `0x180020bf0`
- `0x180080420`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800806c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080611`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800806c0`
- `KERNEL32!CreateFileW` at `0x1800806b0`
- `KERNEL32!CreateFileW` at `0x1800806b0`
- `KERNEL32!GetFileAttributesW` at `0x1800805e3`
- `KERNEL32!GetFileAttributesW` at `0x1800805e3`

## pseudocode

```c
__int64 __fastcall CRdpSettingsFileStream::DoOpenForWrite(
        CRdpSettingsFileStream *this,
        const unsigned __int16 *a2,
        int a3,
        int a4)
{
  int v7; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  const WCHAR *v11; // r14
  __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  DWORD dwFlagsAndAttributes; // eax
  PVOID *v16; // rax
  DWORD LastError; // ebx
  unsigned int v18; // eax
  unsigned int v19; // eax
  HANDLE FileW; // rax
  signed int v21; // eax

  if ( a2 )
  {
    v7 = (*(__int64 (__fastcall **)(CRdpSettingsFileStream *))(*(_QWORD *)this + 96LL))(this);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 16;
        v10 = "Unable to initialize file name from moniker!";
LABEL_7:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v10,
          v7);
        return (unsigned int)v7;
      }
      return (unsigned int)v7;
    }
    v11 = (const WCHAR *)((char *)this + 108);
  }
  else
  {
    v11 = (const WCHAR *)((char *)this + 108);
    if ( !*((_WORD *)this + 54) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v14);
      }
      return (unsigned int)-2147024773;
    }
    v7 = (*(__int64 (__fastcall **)(CRdpSettingsFileStream *))(*(_QWORD *)this + 64LL))(this);
    if ( v7 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 18;
        v10 = "Failed to close file stream!";
        goto LABEL_7;
      }
      return (unsigned int)v7;
    }
  }
  if ( !*((_QWORD *)this + 11) )
  {
    v12 = PAL_System_MemAlloc(2048);
    *((_QWORD *)this + 11) = v12;
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids, v13);
      }
      return (unsigned int)-2147024882;
    }
    *((_DWORD *)this + 24) = 2048;
  }
  dwFlagsAndAttributes = GetFileAttributesW(v11);
  if ( dwFlagsAndAttributes == -1 )
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
          v18,
          LastError);
        v16 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 3u )
      {
        v19 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          (unsigned int)WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids,
          v19,
          (__int64)v11);
      }
    }
    dwFlagsAndAttributes = 128;
  }
  FileW = CreateFileW(v11, 0x40000000u, a4 != 0 ? 3 : 1, 0, 2u, dwFlagsAndAttributes, 0);
  *((_QWORD *)this + 10) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v21 = GetLastError();
    v7 = v21;
    if ( v21 > 0 )
      return (unsigned __int16)v21 | 0x80070000;
  }
  else
  {
    *((_DWORD *)this + 19) = 1;
    *((_DWORD *)this + 158) = a3;
    *((_DWORD *)this + 159) = 1;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180080420  push    rbx
0x180080422  push    rbp
0x180080423  push    rsi
0x180080424  push    rdi
0x180080425  push    r12
0x180080427  push    r13
0x180080429  push    r14
0x18008042b  push    r15
0x18008042d  sub     rsp, 48h
0x180080431  xor     r13d, r13d
0x180080434  mov     r12d, r9d
0x180080437  mov     r15d, r8d
0x18008043a  mov     rsi, rcx
0x18008043d  test    rdx, rdx
0x180080440  jz      loc_18008052F
0x180080446  mov     rax, [rcx]
0x180080449  mov     rax, [rax+60h]
0x18008044d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080452  mov     edi, eax
0x180080454  test    eax, eax
0x180080456  jns     short loc_1800804BB
0x180080458  mov     rax, cs:WPP_GLOBAL_Control
0x18008045f  lea     rbp, WPP_GLOBAL_Control
0x180080466  cmp     rax, rbp
0x180080469  jz      loc_1800806EF
0x18008046f  test    byte ptr [rax+1Ch], 8
0x180080473  jz      loc_1800806EF
0x180080479  cmp     byte ptr [rax+19h], 2
0x18008047d  jb      loc_1800806EF
0x180080483  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180080488  lea     edx, [r13+10h]
0x18008048c  lea     rcx, aUnableToInitia; "Unable to initialize file name from mon"...
0x180080493  mov     [rsp+88h+dwFlagsAndAttributes], edi
0x180080497  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x18008049e  mov     qword ptr [rsp+88h+dwCreationDisposition], rcx
0x1800804a3  mov     r9d, eax
0x1800804a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800804ad  mov     rcx, [rcx+10h]
0x1800804b1  call    WPP_SF_DsD
0x1800804b6  jmp     loc_1800806EF
0x1800804bb  lea     r14, [rsi+6Ch]
0x1800804bf  cmp     [rsi+58h], r13
0x1800804c3  jnz     loc_1800805E0
0x1800804c9  mov     ebx, 800h
0x1800804ce  mov     ecx, ebx
0x1800804d0  call    PAL_System_MemAlloc
0x1800804d5  mov     [rsi+58h], rax
0x1800804d9  test    rax, rax
0x1800804dc  jnz     loc_1800805DD
0x1800804e2  mov     rax, cs:WPP_GLOBAL_Control
0x1800804e9  lea     rbp, WPP_GLOBAL_Control
0x1800804f0  cmp     rax, rbp
0x1800804f3  jz      short loc_180080525
0x1800804f5  test    byte ptr [rax+1Ch], 1
0x1800804f9  jz      short loc_180080525
0x1800804fb  cmp     byte ptr [rax+19h], 2
0x1800804ff  jb      short loc_180080525
0x180080501  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180080506  mov     rcx, cs:WPP_GLOBAL_Control
0x18008050d  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x180080514  mov     edx, 13h
0x180080519  mov     r9d, eax
0x18008051c  mov     rcx, [rcx+10h]
0x180080520  call    WPP_SF_D
0x180080525  mov     edi, 8007000Eh
0x18008052a  jmp     loc_1800806EF
0x18008052f  lea     r14, [rcx+6Ch]
0x180080533  cmp     [r14], r13w
0x180080537  jnz     short loc_180080586
0x180080539  mov     rax, cs:WPP_GLOBAL_Control
0x180080540  lea     rbp, WPP_GLOBAL_Control
0x180080547  cmp     rax, rbp
0x18008054a  jz      short loc_18008057C
0x18008054c  test    byte ptr [rax+1Ch], 1
0x180080550  jz      short loc_18008057C
0x180080552  cmp     byte ptr [rax+19h], 2
0x180080556  jb      short loc_18008057C
0x180080558  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008055d  mov     rcx, cs:WPP_GLOBAL_Control
0x180080564  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x18008056b  mov     edx, 11h
0x180080570  mov     r9d, eax
0x180080573  mov     rcx, [rcx+10h]
0x180080577  call    WPP_SF_D
0x18008057c  mov     edi, 8007007Bh
0x180080581  jmp     loc_1800806EF
0x180080586  mov     rax, [rcx]
0x180080589  mov     rax, [rax+40h]
0x18008058d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080592  mov     edi, eax
0x180080594  test    eax, eax
0x180080596  jns     loc_1800804BF
0x18008059c  mov     rax, cs:WPP_GLOBAL_Control
0x1800805a3  lea     rbp, WPP_GLOBAL_Control
0x1800805aa  cmp     rax, rbp
0x1800805ad  jz      loc_1800806EF
0x1800805b3  test    byte ptr [rax+1Ch], 8
0x1800805b7  jz      loc_1800806EF
0x1800805bd  cmp     byte ptr [rax+19h], 2
0x1800805c1  jb      loc_1800806EF
0x1800805c7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800805cc  mov     edx, 12h
0x1800805d1  lea     rcx, aFailedToCloseF; "Failed to close file stream!"
0x1800805d8  jmp     loc_180080493
0x1800805dd  mov     [rsi+60h], ebx
0x1800805e0  mov     rcx, r14; lpFileName
0x1800805e3  call    cs:__imp_GetFileAttributesW
0x1800805e9  cmp     eax, 0FFFFFFFFh
0x1800805ec  jnz     loc_180080687
0x1800805f2  mov     rax, cs:WPP_GLOBAL_Control
0x1800805f9  lea     rbp, WPP_GLOBAL_Control
0x180080600  cmp     rax, rbp
0x180080603  jz      short loc_180080682
0x180080605  test    byte ptr [rax+1Ch], 1
0x180080609  jz      short loc_180080648
0x18008060b  cmp     byte ptr [rax+19h], 2
0x18008060f  jb      short loc_180080648
0x180080611  call    cs:__imp_GetLastError
0x180080617  mov     ebx, eax
0x180080619  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008061e  mov     rcx, cs:WPP_GLOBAL_Control
0x180080625  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x18008062c  mov     edx, 14h
0x180080631  mov     [rsp+88h+dwCreationDisposition], ebx
0x180080635  mov     r9d, eax
0x180080638  mov     rcx, [rcx+10h]
0x18008063c  call    WPP_SF_Dd
0x180080641  mov     rax, cs:WPP_GLOBAL_Control
0x180080648  cmp     rax, rbp
0x18008064b  jz      short loc_180080682
0x18008064d  test    byte ptr [rax+1Ch], 1
0x180080651  jz      short loc_180080682
0x180080653  cmp     byte ptr [rax+19h], 3
0x180080657  jb      short loc_180080682
0x180080659  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18008065e  mov     rcx, cs:WPP_GLOBAL_Control
0x180080665  lea     r8, WPP_e852207c14a032b2fd4be7ca00df11bb_Traceguids
0x18008066c  mov     edx, 15h
0x180080671  mov     qword ptr [rsp+88h+dwCreationDisposition], r14
0x180080676  mov     r9d, eax
0x180080679  mov     rcx, [rcx+10h]
0x18008067d  call    WPP_SF_DS
0x180080682  mov     eax, 80h
0x180080687  mov     [rsp+88h+hTemplateFile], r13; hTemplateFile
0x18008068c  neg     r12d
0x18008068f  mov     [rsp+88h+dwFlagsAndAttributes], eax; dwFlagsAndAttributes
0x180080693  mov     edx, 40000000h; dwDesiredAccess
0x180080698  sbb     r8d, r8d
0x18008069b  mov     [rsp+88h+dwCreationDisposition], 2; dwCreationDisposition
0x1800806a3  and     r8d, 2
0x1800806a7  xor     r9d, r9d; lpSecurityAttributes
0x1800806aa  inc     r8d; dwShareMode
0x1800806ad  mov     rcx, r14; lpFileName
0x1800806b0  call    cs:__imp_CreateFileW
0x1800806b6  mov     [rsi+50h], rax
0x1800806ba  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800806be  jnz     short loc_1800806D7
0x1800806c0  call    cs:__imp_GetLastError
0x1800806c6  mov     edi, eax
0x1800806c8  test    eax, eax
0x1800806ca  jle     short loc_1800806EF
0x1800806cc  movzx   edi, ax
0x1800806cf  or      edi, 80070000h
0x1800806d5  jmp     short loc_1800806EF
0x1800806d7  mov     dword ptr [rsi+4Ch], 1
0x1800806de  mov     [rsi+278h], r15d
0x1800806e5  mov     dword ptr [rsi+27Ch], 1
0x1800806ef  mov     eax, edi
0x1800806f1  add     rsp, 48h
0x1800806f5  pop     r15
0x1800806f7  pop     r14
0x1800806f9  pop     r13
0x1800806fb  pop     r12
0x1800806fd  pop     rdi
0x1800806fe  pop     rsi
0x1800806ff  pop     rbp
0x180080700  pop     rbx
0x180080701  retn
```
