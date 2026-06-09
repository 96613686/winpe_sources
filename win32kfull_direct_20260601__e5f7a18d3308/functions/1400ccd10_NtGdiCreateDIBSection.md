# NtGdiCreateDIBSection

- ea: `0x1400ccd10`
- end: `0x1400cd25a`
- name: `NtGdiCreateDIBSection`
- size: `1354`
- prototype: `__int64 __usercall@<rax>(HDC@<rcx>, unsigned int, unsigned int, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400a6f1c`
- `0x1400a8e1c`
- `0x1400ccd10`
- `0x1400cd260`
- `0x1400cd314`

## import_xrefs

- `ntoskrnl!ZwUnmapViewOfSection` at `0x1400cd249`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x1400cd249`
- `ntoskrnl!RtlRaiseStatus` at `0x1400ccdde`
- `ntoskrnl!RtlRaiseStatus` at `0x1400ccdde`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1400cd230`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x1400cd230`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1400ccea0`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1400ccea0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400cd1d6`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x1400cd1d6`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1400ccfa3`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1400ccfa3`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400cce07`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400ccffa`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400cce07`
- `win32kbase!FreeThreadBufferWithTag` at `0x1400ccffa`
- `win32kbase!?bDeleteSurface@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHSURF__@@@Z` at `0x1400cd1e8`
- `win32kbase!?bDeleteSurface@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHSURF__@@@Z` at `0x1400cd1e8`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x1400cd176`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x1400cd176`
- `win32kbase!EngSetLastError` at `0x1400ccdf1`
- `win32kbase!EngSetLastError` at `0x1400ccfc2`
- `win32kbase!EngSetLastError` at `0x1400cd021`
- `win32kbase!EngSetLastError` at `0x1400cd189`
- `win32kbase!EngSetLastError` at `0x1400cd1a1`
- `win32kbase!EngSetLastError` at `0x1400cd1c0`
- `win32kbase!EngSetLastError` at `0x1400ccdf1`
- `win32kbase!EngSetLastError` at `0x1400ccfc2`
- `win32kbase!EngSetLastError` at `0x1400cd021`
- `win32kbase!EngSetLastError` at `0x1400cd189`
- `win32kbase!EngSetLastError` at `0x1400cd1a1`
- `win32kbase!EngSetLastError` at `0x1400cd1c0`
- `win32kbase!?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z` at `0x1400cd0e3`
- `win32kbase!?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z` at `0x1400cd0e3`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x1400cd15d`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x1400cd15d`
- `win32kbase!??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z` at `0x1400cd076`
- `win32kbase!??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z` at `0x1400cd076`
- `win32kbase!?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z` at `0x1400cceea`
- `win32kbase!?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z` at `0x1400cceea`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x1400cd203`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x1400cd203`

## pseudocode

```c
HSURF __fastcall NtGdiCreateDIBSection(
        HDC a1,
        __int64 a2,
        int a3,
        struct tagBITMAPINFO *a4,
        unsigned int a5,
        unsigned int a6,
        char a7,
        __int64 a8,
        void *a9)
{
  HSURF DIBitmap; // rdi
  int DCDpiScaleValue; // r8d
  struct tagBITMAPINFO *v14; // rcx
  int v15; // r10d
  LONG biHeight; // eax
  LONG biWidth; // edx
  LONG v18; // eax
  __int64 v19; // r9
  NTSTATUS v20; // esi
  int v21; // esi
  void *v22; // rax
  void *v23; // r14
  Gre::Base *v24; // rcx
  void *v26; // rax
  int v27; // ecx
  struct Gre::Base::SESSION_GLOBALS *v28; // rax
  ULONG_PTR RegionSize; // [rsp+70h] [rbp-A8h] BYREF
  struct tagBITMAPINFO *v30; // [rsp+78h] [rbp-A0h] BYREF
  PVOID v31; // [rsp+80h] [rbp-98h] BYREF
  int v32; // [rsp+88h] [rbp-90h]
  HSURF v33; // [rsp+90h] [rbp-88h]
  PVOID BaseAddress; // [rsp+98h] [rbp-80h] BYREF
  __int64 v35; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v36; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-60h]
  void *v39; // [rsp+C0h] [rbp-58h]
  ULONG_PTR v40; // [rsp+C8h] [rbp-50h]
  int v41; // [rsp+D0h] [rbp-48h]

  DIBitmap = 0;
  v33 = 0;
  if ( a4 )
  {
    v30 = 0;
    BaseAddress = 0;
    bCaptureBitmapInfo(a4, a5, a6, &v30);
    if ( (a7 & 0x10) != 0 )
    {
      DCDpiScaleValue = GreGetDCDpiScaleValue(a1);
      if ( DCDpiScaleValue > 1 )
      {
        v14 = v30;
        v15 = 0x7FFFFFFF / DCDpiScaleValue;
        biHeight = -v30->bmiHeader.biHeight;
        if ( v30->bmiHeader.biHeight > 0 )
          biHeight = v30->bmiHeader.biHeight;
        if ( v15 < biHeight )
          goto LABEL_11;
        biWidth = v30->bmiHeader.biWidth;
        v18 = -biWidth;
        if ( biWidth > 0 )
          v18 = v30->bmiHeader.biWidth;
        if ( v15 < v18 )
LABEL_11:
          RtlRaiseStatus(-1073741675);
        v30->bmiHeader.biHeight *= DCDpiScaleValue;
        v14->bmiHeader.biWidth = DCDpiScaleValue * biWidth;
      }
    }
    if ( v30 )
    {
      LODWORD(v33) = GreGetBitmapBitsSize(v30);
      RegionSize = (unsigned int)v33;
      if ( (_DWORD)v33 )
      {
        if ( a2 )
        {
          v31 = (PVOID)(a3 & 0xFFFF0000);
          RegionSize = (unsigned int)v33 + (unsigned __int64)(unsigned __int16)a3;
          v35 = a2;
          LOBYTE(v19) = 1;
          Gre::SectionObj::SectionObj(&v36, &v35, 1, v19);
          if ( v36 )
          {
            v37 = 0;
            v38 = 0;
            v39 = 0;
            v40 = 0;
            v41 = 6;
            if ( (unsigned __int8)Gre::MapViewOfSectionObj::Map(&v37, v36, 1) )
            {
              RegionSize = v40;
              v26 = v39;
              v39 = 0;
              v37 = 0;
              v38 = 0;
              v40 = 0;
              v27 = 6;
              v41 = 6;
              BaseAddress = v26;
              v20 = 0;
            }
            else
            {
              EngSetLastError(0x57u);
              v20 = -1073741811;
              v27 = v41;
            }
            if ( v27 != 6 )
              Gre::MapViewOfSectionObj::Unmap((Gre::MapViewOfSectionObj *)&v37);
          }
          else
          {
            EngSetLastError(0x57u);
            v20 = -1073741811;
          }
          Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v36);
        }
        else
        {
          v20 = ZwAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x3000u, 4u);
          a3 = 0;
          if ( v20 < 0 )
            EngSetLastError(8u);
        }
        if ( v20 >= 0 )
        {
          v21 = 0;
          v32 = 0;
          v31 = (char *)BaseAddress + (unsigned __int16)a3;
          v22 = GrepSecureVirtualMemory(BaseAddress, RegionSize, 4u);
          v23 = v22;
          v35 = (__int64)v22;
          if ( !v22 )
            goto LABEL_24;
          DIBitmap = (HSURF)GreCreateDIBitmap(
                              (_DWORD)a1,
                              2,
                              (_DWORD)v31,
                              (_DWORD)v30,
                              a5,
                              a6,
                              (_DWORD)v33,
                              a2,
                              a3,
                              (__int64)v22,
                              a7 & 0x14 | 2u,
                              a8);
          v33 = DIBitmap;
          if ( DIBitmap )
          {
            GreProbeAndWriteToUntrustedVa(a9, 8u, &v31, 8u, 1u);
            v21 = 1;
            v32 = 1;
          }
          else
          {
LABEL_24:
            EngSetLastError(0x57u);
          }
          if ( !v21 )
          {
            if ( DIBitmap )
            {
              v28 = Gre::Base::Globals(v24);
              bDeleteSurface(v28, DIBitmap);
              DIBitmap = 0;
            }
            else
            {
              if ( v23 )
                GrepUnsecureVirtualMemory(v23);
              if ( a2 )
              {
                ZwUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
              }
              else
              {
                RegionSize = 0;
                ZwFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &v31, &RegionSize, 0x8000u);
              }
            }
          }
        }
      }
      FreeThreadBufferWithTag(v30);
    }
  }
  return DIBitmap;
}

```

## disassembly

```asm
0x1400ccd10  mov     r11, rsp
0x1400ccd13  mov     [r11+18h], r8d
0x1400ccd17  mov     [r11+10h], rdx
0x1400ccd1b  mov     [r11+8], rcx
0x1400ccd1f  push    rsi
0x1400ccd20  push    rdi
0x1400ccd21  push    r12
0x1400ccd23  push    r13
0x1400ccd25  push    r14
0x1400ccd27  push    r15
0x1400ccd29  sub     rsp, 0E8h
0x1400ccd30  mov     rax, r9
0x1400ccd33  mov     r12d, r8d
0x1400ccd36  mov     r15, rdx
0x1400ccd39  mov     r13, rcx
0x1400ccd3c  xor     edi, edi
0x1400ccd3e  mov     [rsp+118h+var_88], rdi
0x1400ccd46  test    r9, r9
0x1400ccd49  jz      loc_1400CD006
0x1400ccd4f  mov     [rsp+118h+var_A0], rdi
0x1400ccd54  mov     [r11-80h], rdi
0x1400ccd58  lea     r9, [rsp+118h+var_A0]; struct tagBITMAPINFO **
0x1400ccd5d  mov     r8d, [rsp+118h+arg_28]; unsigned int
0x1400ccd65  mov     edx, [rsp+118h+arg_20]; unsigned int
0x1400ccd6c  mov     rcx, rax; struct tagBITMAPINFO *
0x1400ccd6f  call    ?bCaptureBitmapInfo@@YAHPEAUtagBITMAPINFO@@KIPEAPEAU1@@Z; bCaptureBitmapInfo(tagBITMAPINFO *,ulong,uint,tagBITMAPINFO * *)
0x1400ccd74  mov     eax, dword ptr [rsp+118h+arg_30]
0x1400ccd7b  mov     [rsp+118h+arg_18], eax
0x1400ccd82  test    al, 10h
0x1400ccd84  jz      short loc_1400CCDEA
0x1400ccd86  mov     rcx, r13; HDC
0x1400ccd89  call    GreGetDCDpiScaleValue
0x1400ccd8e  mov     r8d, eax
0x1400ccd91  cmp     eax, 1
0x1400ccd94  jle     short loc_1400CCDEA
0x1400ccd96  mov     rcx, [rsp+118h+var_A0]
0x1400ccd9b  mov     r9d, [rcx+8]
0x1400ccd9f  mov     eax, 7FFFFFFFh
0x1400ccda4  cdq
0x1400ccda5  idiv    r8d
0x1400ccda8  mov     r10d, eax
0x1400ccdab  mov     eax, r9d
0x1400ccdae  neg     eax
0x1400ccdb0  cmovs   eax, r9d
0x1400ccdb4  cmp     r10d, eax
0x1400ccdb7  jl      short loc_1400CCDD9
0x1400ccdb9  mov     edx, [rcx+4]
0x1400ccdbc  mov     eax, edx
0x1400ccdbe  neg     eax
0x1400ccdc0  cmovs   eax, edx
0x1400ccdc3  cmp     r10d, eax
0x1400ccdc6  jl      short loc_1400CCDD9
0x1400ccdc8  imul    r9d, r8d
0x1400ccdcc  mov     [rcx+8], r9d
0x1400ccdd0  imul    edx, r8d
0x1400ccdd4  mov     [rcx+4], edx
0x1400ccdd7  jmp     short loc_1400CCDEA
0x1400ccdd9  mov     ecx, 0C0000095h; Status
0x1400ccdde  call    cs:__imp_RtlRaiseStatus
0x1400ccde5  nop     dword ptr [rax+rax+00h]
0x1400ccdea  jmp     short loc_1400CCE4A
0x1400ccdec  mov     ecx, 57h ; 'W'; iError
0x1400ccdf1  call    cs:__imp_EngSetLastError
0x1400ccdf8  nop     dword ptr [rax+rax+00h]
0x1400ccdfd  mov     rcx, [rsp+118h+var_A0]
0x1400cce02  test    rcx, rcx
0x1400cce05  jz      short loc_1400CCE1C
0x1400cce07  call    cs:__imp_FreeThreadBufferWithTag
0x1400cce0e  nop     dword ptr [rax+rax+00h]
0x1400cce13  mov     [rsp+118h+var_A0], 0
0x1400cce1c  mov     eax, dword ptr [rsp+118h+arg_30]
0x1400cce23  mov     [rsp+118h+arg_18], eax
0x1400cce2a  mov     r12d, [rsp+118h+arg_10]
0x1400cce32  mov     r15, [rsp+118h+arg_8]
0x1400cce3a  mov     r13, [rsp+118h+arg_0]
0x1400cce42  mov     rdi, [rsp+118h+var_88]
0x1400cce4a  mov     rcx, [rsp+118h+var_A0]
0x1400cce4f  test    rcx, rcx
0x1400cce52  jz      loc_1400CD006
0x1400cce58  call    GreGetBitmapBitsSize
0x1400cce5d  mov     dword ptr [rsp+118h+var_88], eax
0x1400cce64  mov     edx, eax
0x1400cce66  mov     [rsp+118h+RegionSize], rdx
0x1400cce6b  test    eax, eax
0x1400cce6d  jz      loc_1400CCFF5
0x1400cce73  test    r15, r15
0x1400cce76  jnz     loc_1400CD02F
0x1400cce7c  mov     [rsp+118h+Protect], 4; Protect
0x1400cce84  mov     [rsp+118h+AllocationType], 3000h; AllocationType
0x1400cce8c  lea     r9, [rsp+118h+RegionSize]; RegionSize
0x1400cce91  xor     r8d, r8d; ZeroBits
0x1400cce94  lea     rdx, [rsp+118h+BaseAddress]; BaseAddress
0x1400cce9c  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400ccea0  call    cs:__imp_ZwAllocateVirtualMemory
0x1400ccea7  nop     dword ptr [rax+rax+00h]
0x1400cceac  mov     esi, eax
0x1400cceae  xor     r12d, r12d
0x1400cceb1  test    eax, eax
0x1400cceb3  js      loc_1400CD1BB
0x1400cceb9  test    esi, esi
0x1400ccebb  js      loc_1400CCFF5
0x1400ccec1  xor     esi, esi
0x1400ccec3  mov     [rsp+118h+var_90], esi
0x1400cceca  movzx   edx, r12w
0x1400ccece  mov     rcx, [rsp+118h+BaseAddress]
0x1400cced6  add     rdx, rcx
0x1400cced9  mov     [rsp+118h+var_98], rdx
0x1400ccee1  lea     r8d, [rsi+4]
0x1400ccee5  mov     rdx, [rsp+118h+RegionSize]
0x1400cceea  call    cs:__imp_?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z; GrepSecureVirtualMemory(void *,unsigned __int64,uint)
0x1400ccef1  nop     dword ptr [rax+rax+00h]
0x1400ccef6  mov     r14, rax
0x1400ccef9  mov     [rsp+118h+var_78], rax
0x1400ccf01  test    rax, rax
0x1400ccf04  jz      loc_1400CD01C
0x1400ccf0a  mov     ecx, [rsp+118h+arg_18]
0x1400ccf11  and     ecx, 14h
0x1400ccf14  lea     edx, [rsi+2]
0x1400ccf17  or      ecx, edx
0x1400ccf19  mov     rax, [rsp+118h+arg_38]
0x1400ccf21  mov     [rsp+118h+var_C0], rax
0x1400ccf26  mov     [rsp+118h+var_C8], ecx
0x1400ccf2a  mov     [rsp+118h+var_D0], r14
0x1400ccf2f  mov     [rsp+118h+var_D8], r12d
0x1400ccf34  mov     [rsp+118h+var_E0], r15
0x1400ccf39  mov     eax, dword ptr [rsp+118h+var_88]
0x1400ccf40  mov     [rsp+118h+var_E8], eax
0x1400ccf44  mov     eax, [rsp+118h+arg_28]
0x1400ccf4b  mov     [rsp+118h+Protect], eax
0x1400ccf4f  mov     eax, [rsp+118h+arg_20]
0x1400ccf56  mov     [rsp+118h+AllocationType], eax
0x1400ccf5a  mov     r9, [rsp+118h+var_A0]
0x1400ccf5f  mov     r8, [rsp+118h+var_98]
0x1400ccf67  mov     rcx, r13
0x1400ccf6a  call    GreCreateDIBitmap
0x1400ccf6f  mov     rdi, rax
0x1400ccf72  mov     [rsp+118h+var_88], rax
0x1400ccf7a  test    rax, rax
0x1400ccf7d  jz      loc_1400CD01C
0x1400ccf83  mov     qword ptr [rsp+118h+AllocationType], 1
0x1400ccf8c  lea     r9d, [rsi+8]
0x1400ccf90  lea     r8, [rsp+118h+var_98]
0x1400ccf98  mov     edx, r9d
0x1400ccf9b  mov     rcx, [rsp+118h+arg_40]
0x1400ccfa3  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x1400ccfaa  nop     dword ptr [rax+rax+00h]
0x1400ccfaf  mov     esi, 1
0x1400ccfb4  mov     [rsp+118h+var_90], esi
0x1400ccfbb  jmp     short loc_1400CCFED
0x1400ccfbd  mov     ecx, 57h ; 'W'; iError
0x1400ccfc2  call    cs:__imp_EngSetLastError
0x1400ccfc9  nop     dword ptr [rax+rax+00h]
0x1400ccfce  mov     r15, [rsp+118h+arg_8]
0x1400ccfd6  mov     rdi, [rsp+118h+var_88]
0x1400ccfde  mov     esi, [rsp+118h+var_90]
0x1400ccfe5  mov     r14, [rsp+118h+var_78]
0x1400ccfed  test    esi, esi
0x1400ccfef  jz      loc_1400CD1D1
0x1400ccff5  mov     rcx, [rsp+118h+var_A0]
0x1400ccffa  call    cs:__imp_FreeThreadBufferWithTag
0x1400cd001  nop     dword ptr [rax+rax+00h]
0x1400cd006  mov     rax, rdi
0x1400cd009  add     rsp, 0E8h
0x1400cd010  pop     r15
0x1400cd012  pop     r14
0x1400cd014  pop     r13
0x1400cd016  pop     r12
0x1400cd018  pop     rdi
0x1400cd019  pop     rsi
0x1400cd01a  retn
0x1400cd01c  mov     ecx, 57h ; 'W'; iError
0x1400cd021  call    cs:__imp_EngSetLastError
0x1400cd028  nop     dword ptr [rax+rax+00h]
0x1400cd02d  jmp     short loc_1400CCFED
0x1400cd02f  mov     eax, r12d
0x1400cd032  and     eax, 0FFFF0000h
0x1400cd037  mov     dword ptr [rsp+118h+var_98], eax
0x1400cd03e  mov     dword ptr [rsp+118h+var_98+4], 0
0x1400cd049  movzx   ecx, r12w
0x1400cd04d  add     rcx, rdx
0x1400cd050  mov     [rsp+118h+RegionSize], rcx
0x1400cd055  mov     [rsp+118h+var_78], r15
0x1400cd05d  mov     r9b, 1
0x1400cd060  mov     r8d, 1
0x1400cd066  lea     rdx, [rsp+118h+var_78]
0x1400cd06e  lea     rcx, [rsp+118h+var_70]
0x1400cd076  call    cs:__imp_??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z; Gre::SectionObj::SectionObj(Gre::SectionObj::SectionHandle &&,Gre::SectionObj::AccessMode,char)
0x1400cd07d  nop     dword ptr [rax+rax+00h]
0x1400cd082  mov     rdx, [rsp+118h+var_70]
0x1400cd08a  test    rdx, rdx
0x1400cd08d  jz      loc_1400CD184
0x1400cd093  mov     [rsp+118h+var_68], 0
0x1400cd09f  xor     eax, eax
0x1400cd0a1  mov     [rsp+118h+var_60], rax
0x1400cd0a9  mov     [rsp+118h+var_58], rax
0x1400cd0b1  mov     [rsp+118h+var_50], rax
0x1400cd0b9  lea     r14d, [rax+6]
0x1400cd0bd  mov     [rsp+118h+var_48], r14d
0x1400cd0c5  lea     rax, [rsp+118h+var_98]
0x1400cd0cd  mov     qword ptr [rsp+118h+AllocationType], rax
0x1400cd0d2  mov     r9, [rsp+118h+RegionSize]
0x1400cd0d7  lea     r8d, [r14-5]
0x1400cd0db  lea     rcx, [rsp+118h+var_68]
0x1400cd0e3  call    cs:__imp_?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z; Gre::MapViewOfSectionObj::Map(void *,Gre::MapViewOfSectionObj::MapKind,unsigned __int64,_LARGE_INTEGER *)
0x1400cd0ea  nop     dword ptr [rax+rax+00h]
0x1400cd0ef  test    al, al
0x1400cd0f1  jz      loc_1400CD19C
0x1400cd0f7  mov     rax, [rsp+118h+var_50]
0x1400cd0ff  mov     [rsp+118h+RegionSize], rax
0x1400cd104  mov     rax, [rsp+118h+var_58]
0x1400cd10c  mov     [rsp+118h+var_58], 0
0x1400cd118  mov     [rsp+118h+var_68], 0
0x1400cd124  mov     [rsp+118h+var_60], 0
0x1400cd130  mov     [rsp+118h+var_50], 0
0x1400cd13c  mov     ecx, r14d
0x1400cd13f  mov     [rsp+118h+var_48], ecx
0x1400cd146  mov     [rsp+118h+BaseAddress], rax
0x1400cd14e  xor     esi, esi
0x1400cd150  cmp     ecx, r14d
0x1400cd153  jnz     short loc_1400CD16E
0x1400cd155  lea     rcx, [rsp+118h+var_70]
0x1400cd15d  call    cs:__imp_??1SectionObj@Gre@@QEAA@XZ; Gre::SectionObj::~SectionObj(void)
0x1400cd164  nop     dword ptr [rax+rax+00h]
0x1400cd169  jmp     loc_1400CCEB9
0x1400cd16e  lea     rcx, [rsp+118h+var_68]
0x1400cd176  call    cs:__imp_?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ; Gre::MapViewOfSectionObj::Unmap(void)
0x1400cd17d  nop     dword ptr [rax+rax+00h]
0x1400cd182  jmp     short loc_1400CD155
0x1400cd184  mov     ecx, 57h ; 'W'; iError
0x1400cd189  call    cs:__imp_EngSetLastError
0x1400cd190  nop     dword ptr [rax+rax+00h]
0x1400cd195  mov     esi, 0C000000Dh
0x1400cd19a  jmp     short loc_1400CD155
0x1400cd19c  mov     ecx, 57h ; 'W'; iError
0x1400cd1a1  call    cs:__imp_EngSetLastError
0x1400cd1a8  nop     dword ptr [rax+rax+00h]
0x1400cd1ad  mov     esi, 0C000000Dh
0x1400cd1b2  mov     ecx, [rsp+118h+var_48]
0x1400cd1b9  jmp     short loc_1400CD150
0x1400cd1bb  mov     ecx, 8; iError
0x1400cd1c0  call    cs:__imp_EngSetLastError
0x1400cd1c7  nop     dword ptr [rax+rax+00h]
0x1400cd1cc  jmp     loc_1400CCEB9
0x1400cd1d1  test    rdi, rdi
0x1400cd1d4  jz      short loc_1400CD1FB
0x1400cd1d6  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x1400cd1dd  nop     dword ptr [rax+rax+00h]
0x1400cd1e2  mov     rdx, rdi
0x1400cd1e5  mov     rcx, rax
0x1400cd1e8  call    cs:__imp_?bDeleteSurface@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHSURF__@@@Z; bDeleteSurface(Gre::Base::SESSION_GLOBALS &,HSURF__ *)
0x1400cd1ef  nop     dword ptr [rax+rax+00h]
0x1400cd1f4  xor     edi, edi
0x1400cd1f6  jmp     loc_1400CCFF5
0x1400cd1fb  test    r14, r14
0x1400cd1fe  jz      short loc_1400CD20F
0x1400cd200  mov     rcx, r14
0x1400cd203  call    cs:__imp_?GrepUnsecureVirtualMemory@@YAXPEAX@Z; GrepUnsecureVirtualMemory(void *)
0x1400cd20a  nop     dword ptr [rax+rax+00h]
0x1400cd20f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400cd213  test    r15, r15
0x1400cd216  jnz     short loc_1400CD241
0x1400cd218  mov     [rsp+118h+RegionSize], r15
0x1400cd21d  mov     r9d, 8000h; FreeType
0x1400cd223  lea     r8, [rsp+118h+RegionSize]; RegionSize
0x1400cd228  lea     rdx, [rsp+118h+var_98]; BaseAddress
0x1400cd230  call    cs:__imp_ZwFreeVirtualMemory
0x1400cd237  nop     dword ptr [rax+rax+00h]
0x1400cd23c  jmp     loc_1400CCFF5
0x1400cd241  mov     rdx, [rsp+118h+BaseAddress]; BaseAddress
0x1400cd249  call    cs:__imp_ZwUnmapViewOfSection
0x1400cd250  nop     dword ptr [rax+rax+00h]
0x1400cd255  jmp     loc_1400CCFF5
```
