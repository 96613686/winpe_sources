# NtGdiCreateDIBSection

- ea: `0x140151450`
- end: `0x14015199a`
- name: `NtGdiCreateDIBSection`
- size: `1354`
- prototype: `HSURF __fastcall(HDC, void *, int, struct tagBITMAPINFO *, unsigned int, unsigned int, char, __int64, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140060dd8`
- `0x140150f98`
- `0x140151398`
- `0x140151450`
- `0x14015317c`

## import_xrefs

- `ntoskrnl!ZwUnmapViewOfSection` at `0x140151989`
- `ntoskrnl!ZwUnmapViewOfSection` at `0x140151989`
- `ntoskrnl!RtlRaiseStatus` at `0x14015151e`
- `ntoskrnl!RtlRaiseStatus` at `0x14015151e`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x140151970`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x140151970`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1401515e0`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x1401515e0`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140151916`
- `win32kbase!?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ` at `0x140151916`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1401516e3`
- `win32kbase!?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z` at `0x1401516e3`
- `win32kbase!FreeThreadBufferWithTag` at `0x140151547`
- `win32kbase!FreeThreadBufferWithTag` at `0x14015173a`
- `win32kbase!FreeThreadBufferWithTag` at `0x140151547`
- `win32kbase!FreeThreadBufferWithTag` at `0x14015173a`
- `win32kbase!?bDeleteSurface@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHSURF__@@@Z` at `0x140151928`
- `win32kbase!?bDeleteSurface@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHSURF__@@@Z` at `0x140151928`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x1401518b6`
- `win32kbase!?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ` at `0x1401518b6`
- `win32kbase!EngSetLastError` at `0x140151531`
- `win32kbase!EngSetLastError` at `0x140151702`
- `win32kbase!EngSetLastError` at `0x140151761`
- `win32kbase!EngSetLastError` at `0x1401518c9`
- `win32kbase!EngSetLastError` at `0x1401518e1`
- `win32kbase!EngSetLastError` at `0x140151900`
- `win32kbase!EngSetLastError` at `0x140151531`
- `win32kbase!EngSetLastError` at `0x140151702`
- `win32kbase!EngSetLastError` at `0x140151761`
- `win32kbase!EngSetLastError` at `0x1401518c9`
- `win32kbase!EngSetLastError` at `0x1401518e1`
- `win32kbase!EngSetLastError` at `0x140151900`
- `win32kbase!?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z` at `0x140151823`
- `win32kbase!?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z` at `0x140151823`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14015189d`
- `win32kbase!??1SectionObj@Gre@@QEAA@XZ` at `0x14015189d`
- `win32kbase!??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z` at `0x1401517b6`
- `win32kbase!??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z` at `0x1401517b6`
- `win32kbase!?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z` at `0x14015162a`
- `win32kbase!?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z` at `0x14015162a`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x140151943`
- `win32kbase!?GrepUnsecureVirtualMemory@@YAXPEAX@Z` at `0x140151943`

## pseudocode

```c
HSURF __fastcall NtGdiCreateDIBSection(
        HDC a1,
        void *a2,
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
  PVOID *AllocationType; // [rsp+20h] [rbp-F8h]
  ULONG_PTR RegionSize; // [rsp+70h] [rbp-A8h] BYREF
  struct tagBITMAPINFO *v31; // [rsp+78h] [rbp-A0h] BYREF
  PVOID v32; // [rsp+80h] [rbp-98h] BYREF
  int v33; // [rsp+88h] [rbp-90h]
  HSURF v34; // [rsp+90h] [rbp-88h]
  PVOID BaseAddress; // [rsp+98h] [rbp-80h] BYREF
  void *v36; // [rsp+A0h] [rbp-78h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-68h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-60h]
  void *v40; // [rsp+C0h] [rbp-58h]
  ULONG_PTR v41; // [rsp+C8h] [rbp-50h]
  int v42; // [rsp+D0h] [rbp-48h]

  DIBitmap = 0;
  v34 = 0;
  if ( a4 )
  {
    v31 = 0;
    BaseAddress = 0;
    bCaptureBitmapInfo(a4, a5, a6, &v31);
    if ( (a7 & 0x10) != 0 )
    {
      DCDpiScaleValue = GreGetDCDpiScaleValue(a1);
      if ( DCDpiScaleValue > 1 )
      {
        v14 = v31;
        v15 = 0x7FFFFFFF / DCDpiScaleValue;
        biHeight = -v31->bmiHeader.biHeight;
        if ( v31->bmiHeader.biHeight > 0 )
          biHeight = v31->bmiHeader.biHeight;
        if ( v15 < biHeight )
          goto LABEL_11;
        biWidth = v31->bmiHeader.biWidth;
        v18 = -biWidth;
        if ( biWidth > 0 )
          v18 = v31->bmiHeader.biWidth;
        if ( v15 < v18 )
LABEL_11:
          RtlRaiseStatus(-1073741675);
        v31->bmiHeader.biHeight *= DCDpiScaleValue;
        v14->bmiHeader.biWidth = DCDpiScaleValue * biWidth;
      }
    }
    if ( v31 )
    {
      LODWORD(v34) = GreGetBitmapBitsSize((__int64)v31);
      RegionSize = (unsigned int)v34;
      if ( (_DWORD)v34 )
      {
        if ( a2 )
        {
          v32 = (PVOID)(a3 & 0xFFFF0000);
          RegionSize = (unsigned int)v34 + (unsigned __int64)(unsigned __int16)a3;
          v36 = a2;
          LOBYTE(v19) = 1;
          Gre::SectionObj::SectionObj(&v37, &v36, 1, v19);
          if ( v37 )
          {
            v38 = 0;
            v39 = 0;
            v40 = 0;
            v41 = 0;
            v42 = 6;
            AllocationType = &v32;
            if ( (unsigned __int8)Gre::MapViewOfSectionObj::Map(&v38, v37, 1) )
            {
              RegionSize = v41;
              v26 = v40;
              v40 = 0;
              v38 = 0;
              v39 = 0;
              v41 = 0;
              v27 = 6;
              v42 = 6;
              BaseAddress = v26;
              v20 = 0;
            }
            else
            {
              EngSetLastError(0x57u);
              v20 = -1073741811;
              v27 = v42;
            }
            if ( v27 != 6 )
              Gre::MapViewOfSectionObj::Unmap((Gre::MapViewOfSectionObj *)&v38);
          }
          else
          {
            EngSetLastError(0x57u);
            v20 = -1073741811;
          }
          Gre::SectionObj::~SectionObj((Gre::SectionObj *)&v37);
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
          v33 = 0;
          v32 = (char *)BaseAddress + (unsigned __int16)a3;
          v22 = GrepSecureVirtualMemory(BaseAddress, RegionSize, 4u);
          v23 = v22;
          v36 = v22;
          if ( !v22 )
            goto LABEL_24;
          LODWORD(AllocationType) = a5;
          DIBitmap = (HSURF)GreCreateDIBitmap(
                              a1,
                              2,
                              v32,
                              v31,
                              AllocationType,
                              a6,
                              (_DWORD)v34,
                              a2,
                              a3,
                              v22,
                              a7 & 0x14 | 2u,
                              a8);
          v34 = DIBitmap;
          if ( DIBitmap )
          {
            GreProbeAndWriteToUntrustedVa(a9, 8u, &v32, 8u, 1u);
            v21 = 1;
            v33 = 1;
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
                ZwFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &v32, &RegionSize, 0x8000u);
              }
            }
          }
        }
      }
      FreeThreadBufferWithTag(v31);
    }
  }
  return DIBitmap;
}

```

## disassembly

```asm
0x140151450  mov     r11, rsp
0x140151453  mov     [r11+18h], r8d
0x140151457  mov     [r11+10h], rdx
0x14015145b  mov     [r11+8], rcx
0x14015145f  push    rsi
0x140151460  push    rdi
0x140151461  push    r12
0x140151463  push    r13
0x140151465  push    r14
0x140151467  push    r15
0x140151469  sub     rsp, 0E8h
0x140151470  mov     rax, r9
0x140151473  mov     r12d, r8d
0x140151476  mov     r15, rdx
0x140151479  mov     r13, rcx
0x14015147c  xor     edi, edi
0x14015147e  mov     [rsp+118h+var_88], rdi
0x140151486  test    r9, r9
0x140151489  jz      loc_140151746
0x14015148f  mov     [rsp+118h+var_A0], rdi
0x140151494  mov     [r11-80h], rdi
0x140151498  lea     r9, [rsp+118h+var_A0]; struct tagBITMAPINFO **
0x14015149d  mov     r8d, [rsp+118h+arg_28]; unsigned int
0x1401514a5  mov     edx, [rsp+118h+arg_20]; unsigned int
0x1401514ac  mov     rcx, rax; struct tagBITMAPINFO *
0x1401514af  call    ?bCaptureBitmapInfo@@YAHPEAUtagBITMAPINFO@@KIPEAPEAU1@@Z; bCaptureBitmapInfo(tagBITMAPINFO *,ulong,uint,tagBITMAPINFO * *)
0x1401514b4  mov     eax, dword ptr [rsp+118h+arg_30]
0x1401514bb  mov     [rsp+118h+arg_18], eax
0x1401514c2  test    al, 10h
0x1401514c4  jz      short loc_14015152A
0x1401514c6  mov     rcx, r13; HDC
0x1401514c9  call    GreGetDCDpiScaleValue
0x1401514ce  mov     r8d, eax
0x1401514d1  cmp     eax, 1
0x1401514d4  jle     short loc_14015152A
0x1401514d6  mov     rcx, [rsp+118h+var_A0]
0x1401514db  mov     r9d, [rcx+8]
0x1401514df  mov     eax, 7FFFFFFFh
0x1401514e4  cdq
0x1401514e5  idiv    r8d
0x1401514e8  mov     r10d, eax
0x1401514eb  mov     eax, r9d
0x1401514ee  neg     eax
0x1401514f0  cmovs   eax, r9d
0x1401514f4  cmp     r10d, eax
0x1401514f7  jl      short loc_140151519
0x1401514f9  mov     edx, [rcx+4]
0x1401514fc  mov     eax, edx
0x1401514fe  neg     eax
0x140151500  cmovs   eax, edx
0x140151503  cmp     r10d, eax
0x140151506  jl      short loc_140151519
0x140151508  imul    r9d, r8d
0x14015150c  mov     [rcx+8], r9d
0x140151510  imul    edx, r8d
0x140151514  mov     [rcx+4], edx
0x140151517  jmp     short loc_14015152A
0x140151519  mov     ecx, 0C0000095h; Status
0x14015151e  call    cs:__imp_RtlRaiseStatus
0x140151525  nop     dword ptr [rax+rax+00h]
0x14015152a  jmp     short loc_14015158A
0x14015152c  mov     ecx, 57h ; 'W'; iError
0x140151531  call    cs:__imp_EngSetLastError
0x140151538  nop     dword ptr [rax+rax+00h]
0x14015153d  mov     rcx, [rsp+118h+var_A0]
0x140151542  test    rcx, rcx
0x140151545  jz      short loc_14015155C
0x140151547  call    cs:__imp_FreeThreadBufferWithTag
0x14015154e  nop     dword ptr [rax+rax+00h]
0x140151553  mov     [rsp+118h+var_A0], 0
0x14015155c  mov     eax, dword ptr [rsp+118h+arg_30]
0x140151563  mov     [rsp+118h+arg_18], eax
0x14015156a  mov     r12d, [rsp+118h+arg_10]
0x140151572  mov     r15, [rsp+118h+arg_8]
0x14015157a  mov     r13, [rsp+118h+arg_0]
0x140151582  mov     rdi, [rsp+118h+var_88]
0x14015158a  mov     rcx, [rsp+118h+var_A0]
0x14015158f  test    rcx, rcx
0x140151592  jz      loc_140151746
0x140151598  call    GreGetBitmapBitsSize
0x14015159d  mov     dword ptr [rsp+118h+var_88], eax
0x1401515a4  mov     edx, eax
0x1401515a6  mov     [rsp+118h+RegionSize], rdx
0x1401515ab  test    eax, eax
0x1401515ad  jz      loc_140151735
0x1401515b3  test    r15, r15
0x1401515b6  jnz     loc_14015176F
0x1401515bc  mov     [rsp+118h+Protect], 4; Protect
0x1401515c4  mov     [rsp+118h+AllocationType], 3000h; AllocationType
0x1401515cc  lea     r9, [rsp+118h+RegionSize]; RegionSize
0x1401515d1  xor     r8d, r8d; ZeroBits
0x1401515d4  lea     rdx, [rsp+118h+BaseAddress]; BaseAddress
0x1401515dc  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1401515e0  call    cs:__imp_ZwAllocateVirtualMemory
0x1401515e7  nop     dword ptr [rax+rax+00h]
0x1401515ec  mov     esi, eax
0x1401515ee  xor     r12d, r12d
0x1401515f1  test    eax, eax
0x1401515f3  js      loc_1401518FB
0x1401515f9  test    esi, esi
0x1401515fb  js      loc_140151735
0x140151601  xor     esi, esi
0x140151603  mov     [rsp+118h+var_90], esi
0x14015160a  movzx   edx, r12w
0x14015160e  mov     rcx, [rsp+118h+BaseAddress]
0x140151616  add     rdx, rcx
0x140151619  mov     [rsp+118h+var_98], rdx
0x140151621  lea     r8d, [rsi+4]
0x140151625  mov     rdx, [rsp+118h+RegionSize]
0x14015162a  call    cs:__imp_?GrepSecureVirtualMemory@@YAPEAXPEAX_KI@Z; GrepSecureVirtualMemory(void *,unsigned __int64,uint)
0x140151631  nop     dword ptr [rax+rax+00h]
0x140151636  mov     r14, rax
0x140151639  mov     [rsp+118h+var_78], rax
0x140151641  test    rax, rax
0x140151644  jz      loc_14015175C
0x14015164a  mov     ecx, [rsp+118h+arg_18]
0x140151651  and     ecx, 14h
0x140151654  lea     edx, [rsi+2]
0x140151657  or      ecx, edx
0x140151659  mov     rax, [rsp+118h+arg_38]
0x140151661  mov     [rsp+118h+var_C0], rax
0x140151666  mov     [rsp+118h+var_C8], ecx
0x14015166a  mov     [rsp+118h+var_D0], r14
0x14015166f  mov     [rsp+118h+var_D8], r12d
0x140151674  mov     [rsp+118h+var_E0], r15
0x140151679  mov     eax, dword ptr [rsp+118h+var_88]
0x140151680  mov     [rsp+118h+var_E8], eax
0x140151684  mov     eax, [rsp+118h+arg_28]
0x14015168b  mov     [rsp+118h+Protect], eax
0x14015168f  mov     eax, [rsp+118h+arg_20]
0x140151696  mov     [rsp+118h+AllocationType], eax
0x14015169a  mov     r9, [rsp+118h+var_A0]
0x14015169f  mov     r8, [rsp+118h+var_98]
0x1401516a7  mov     rcx, r13
0x1401516aa  call    GreCreateDIBitmap
0x1401516af  mov     rdi, rax
0x1401516b2  mov     [rsp+118h+var_88], rax
0x1401516ba  test    rax, rax
0x1401516bd  jz      loc_14015175C
0x1401516c3  mov     qword ptr [rsp+118h+AllocationType], 1
0x1401516cc  lea     r9d, [rsi+8]
0x1401516d0  lea     r8, [rsp+118h+var_98]
0x1401516d8  mov     edx, r9d
0x1401516db  mov     rcx, [rsp+118h+arg_40]
0x1401516e3  call    cs:__imp_?GreProbeAndWriteToUntrustedVa@@YAXPEAX_KPEBX11@Z; GreProbeAndWriteToUntrustedVa(void *,unsigned __int64,void const *,unsigned __int64,unsigned __int64)
0x1401516ea  nop     dword ptr [rax+rax+00h]
0x1401516ef  mov     esi, 1
0x1401516f4  mov     [rsp+118h+var_90], esi
0x1401516fb  jmp     short loc_14015172D
0x1401516fd  mov     ecx, 57h ; 'W'; iError
0x140151702  call    cs:__imp_EngSetLastError
0x140151709  nop     dword ptr [rax+rax+00h]
0x14015170e  mov     r15, [rsp+118h+arg_8]
0x140151716  mov     rdi, [rsp+118h+var_88]
0x14015171e  mov     esi, [rsp+118h+var_90]
0x140151725  mov     r14, [rsp+118h+var_78]
0x14015172d  test    esi, esi
0x14015172f  jz      loc_140151911
0x140151735  mov     rcx, [rsp+118h+var_A0]
0x14015173a  call    cs:__imp_FreeThreadBufferWithTag
0x140151741  nop     dword ptr [rax+rax+00h]
0x140151746  mov     rax, rdi
0x140151749  add     rsp, 0E8h
0x140151750  pop     r15
0x140151752  pop     r14
0x140151754  pop     r13
0x140151756  pop     r12
0x140151758  pop     rdi
0x140151759  pop     rsi
0x14015175a  retn
0x14015175c  mov     ecx, 57h ; 'W'; iError
0x140151761  call    cs:__imp_EngSetLastError
0x140151768  nop     dword ptr [rax+rax+00h]
0x14015176d  jmp     short loc_14015172D
0x14015176f  mov     eax, r12d
0x140151772  and     eax, 0FFFF0000h
0x140151777  mov     dword ptr [rsp+118h+var_98], eax
0x14015177e  mov     dword ptr [rsp+118h+var_98+4], 0
0x140151789  movzx   ecx, r12w
0x14015178d  add     rcx, rdx
0x140151790  mov     [rsp+118h+RegionSize], rcx
0x140151795  mov     [rsp+118h+var_78], r15
0x14015179d  mov     r9b, 1
0x1401517a0  mov     r8d, 1
0x1401517a6  lea     rdx, [rsp+118h+var_78]
0x1401517ae  lea     rcx, [rsp+118h+var_70]
0x1401517b6  call    cs:__imp_??0SectionObj@Gre@@QEAA@$$QEAVSectionHandle@01@W4AccessMode@01@D@Z; Gre::SectionObj::SectionObj(Gre::SectionObj::SectionHandle &&,Gre::SectionObj::AccessMode,char)
0x1401517bd  nop     dword ptr [rax+rax+00h]
0x1401517c2  mov     rdx, [rsp+118h+var_70]
0x1401517ca  test    rdx, rdx
0x1401517cd  jz      loc_1401518C4
0x1401517d3  mov     [rsp+118h+var_68], 0
0x1401517df  xor     eax, eax
0x1401517e1  mov     [rsp+118h+var_60], rax
0x1401517e9  mov     [rsp+118h+var_58], rax
0x1401517f1  mov     [rsp+118h+var_50], rax
0x1401517f9  lea     r14d, [rax+6]
0x1401517fd  mov     [rsp+118h+var_48], r14d
0x140151805  lea     rax, [rsp+118h+var_98]
0x14015180d  mov     qword ptr [rsp+118h+AllocationType], rax
0x140151812  mov     r9, [rsp+118h+RegionSize]
0x140151817  lea     r8d, [r14-5]
0x14015181b  lea     rcx, [rsp+118h+var_68]
0x140151823  call    cs:__imp_?Map@MapViewOfSectionObj@Gre@@QEAA_NPEAXW4MapKind@12@_KPEAT_LARGE_INTEGER@@@Z; Gre::MapViewOfSectionObj::Map(void *,Gre::MapViewOfSectionObj::MapKind,unsigned __int64,_LARGE_INTEGER *)
0x14015182a  nop     dword ptr [rax+rax+00h]
0x14015182f  test    al, al
0x140151831  jz      loc_1401518DC
0x140151837  mov     rax, [rsp+118h+var_50]
0x14015183f  mov     [rsp+118h+RegionSize], rax
0x140151844  mov     rax, [rsp+118h+var_58]
0x14015184c  mov     [rsp+118h+var_58], 0
0x140151858  mov     [rsp+118h+var_68], 0
0x140151864  mov     [rsp+118h+var_60], 0
0x140151870  mov     [rsp+118h+var_50], 0
0x14015187c  mov     ecx, r14d
0x14015187f  mov     [rsp+118h+var_48], ecx
0x140151886  mov     [rsp+118h+BaseAddress], rax
0x14015188e  xor     esi, esi
0x140151890  cmp     ecx, r14d
0x140151893  jnz     short loc_1401518AE
0x140151895  lea     rcx, [rsp+118h+var_70]
0x14015189d  call    cs:__imp_??1SectionObj@Gre@@QEAA@XZ; Gre::SectionObj::~SectionObj(void)
0x1401518a4  nop     dword ptr [rax+rax+00h]
0x1401518a9  jmp     loc_1401515F9
0x1401518ae  lea     rcx, [rsp+118h+var_68]
0x1401518b6  call    cs:__imp_?Unmap@MapViewOfSectionObj@Gre@@QEAA_NXZ; Gre::MapViewOfSectionObj::Unmap(void)
0x1401518bd  nop     dword ptr [rax+rax+00h]
0x1401518c2  jmp     short loc_140151895
0x1401518c4  mov     ecx, 57h ; 'W'; iError
0x1401518c9  call    cs:__imp_EngSetLastError
0x1401518d0  nop     dword ptr [rax+rax+00h]
0x1401518d5  mov     esi, 0C000000Dh
0x1401518da  jmp     short loc_140151895
0x1401518dc  mov     ecx, 57h ; 'W'; iError
0x1401518e1  call    cs:__imp_EngSetLastError
0x1401518e8  nop     dword ptr [rax+rax+00h]
0x1401518ed  mov     esi, 0C000000Dh
0x1401518f2  mov     ecx, [rsp+118h+var_48]
0x1401518f9  jmp     short loc_140151890
0x1401518fb  mov     ecx, 8; iError
0x140151900  call    cs:__imp_EngSetLastError
0x140151907  nop     dword ptr [rax+rax+00h]
0x14015190c  jmp     loc_1401515F9
0x140151911  test    rdi, rdi
0x140151914  jz      short loc_14015193B
0x140151916  call    cs:__imp_?Globals@Base@Gre@@YAAEAUSESSION_GLOBALS@12@XZ; Gre::Base::Globals(void)
0x14015191d  nop     dword ptr [rax+rax+00h]
0x140151922  mov     rdx, rdi
0x140151925  mov     rcx, rax
0x140151928  call    cs:__imp_?bDeleteSurface@@YAHAEAUSESSION_GLOBALS@Base@Gre@@PEAUHSURF__@@@Z; bDeleteSurface(Gre::Base::SESSION_GLOBALS &,HSURF__ *)
0x14015192f  nop     dword ptr [rax+rax+00h]
0x140151934  xor     edi, edi
0x140151936  jmp     loc_140151735
0x14015193b  test    r14, r14
0x14015193e  jz      short loc_14015194F
0x140151940  mov     rcx, r14
0x140151943  call    cs:__imp_?GrepUnsecureVirtualMemory@@YAXPEAX@Z; GrepUnsecureVirtualMemory(void *)
0x14015194a  nop     dword ptr [rax+rax+00h]
0x14015194f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140151953  test    r15, r15
0x140151956  jnz     short loc_140151981
0x140151958  mov     [rsp+118h+RegionSize], r15
0x14015195d  mov     r9d, 8000h; FreeType
0x140151963  lea     r8, [rsp+118h+RegionSize]; RegionSize
0x140151968  lea     rdx, [rsp+118h+var_98]; BaseAddress
0x140151970  call    cs:__imp_ZwFreeVirtualMemory
0x140151977  nop     dword ptr [rax+rax+00h]
0x14015197c  jmp     loc_140151735
0x140151981  mov     rdx, [rsp+118h+BaseAddress]; BaseAddress
0x140151989  call    cs:__imp_ZwUnmapViewOfSection
0x140151990  nop     dword ptr [rax+rax+00h]
0x140151995  jmp     loc_140151735
```
