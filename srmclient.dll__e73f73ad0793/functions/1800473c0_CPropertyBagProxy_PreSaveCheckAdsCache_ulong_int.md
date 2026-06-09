# CPropertyBagProxy::PreSaveCheckAdsCache(ulong,int)

- ea: `0x1800473c0`
- end: `0x180047983`
- name: `?PreSaveCheckAdsCache@CPropertyBagProxy@@UEAAJKH@Z`
- size: `1475`
- prototype: `__int64 __fastcall(CPropertyBagProxy *__hidden this, unsigned int, int)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001350`
- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x18001bc58`
- `0x180044048`
- `0x1800473c0`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180073f54`
- `0x180083a68`
- `0x1800888d0`
- `0x180089a2c`
- `0x18008a024`
- `0x18008b5d4`
- `0x1800b078a`
- `0x1800b07d0`
- `0x1800d5010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18004764d`
- `OLEAUT32!__imp_SysAllocString` at `0x180047798`
- `OLEAUT32!__imp_SysAllocString` at `0x18004764d`
- `OLEAUT32!__imp_SysAllocString` at `0x180047798`
- `OLEAUT32!__imp_SysFreeString` at `0x1800475fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180047733`
- `OLEAUT32!__imp_SysFreeString` at `0x1800475fe`
- `OLEAUT32!__imp_SysFreeString` at `0x180047733`
- `KERNEL32!CompareFileTime` at `0x18004758c`
- `KERNEL32!CompareFileTime` at `0x1800476b9`
- `KERNEL32!CompareFileTime` at `0x18004758c`
- `KERNEL32!CompareFileTime` at `0x1800476b9`

## string_xrefs

- `0x180047401`: `base\fs\fsrm\service\modulewrp\propertybagproxy.cpp`
- `0x180047830`: `File could not be opened because it is encrypted`
- `0x18004740f`: `CPropertyBagProxy::PreSaveCheckAdsCache`
- `0x1800477e9`: `Cache is already open in another process`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPropertyBagProxy::PreSaveCheckAdsCache(CPropertyBagProxy *this, unsigned int a2, int a3)
{
  int v6; // eax
  char *v7; // rdi
  FILETIME v8; // rcx
  struct _FILETIME *v9; // rdx
  struct _FILETIME *v10; // r8
  __int64 v11; // rsi
  void **v12; // rcx
  __int64 v13; // rsi
  OLECHAR *v14; // rcx
  unsigned int v15; // edi
  char Hr; // al
  int v18; // eax
  char v19; // al
  int pExceptionObject; // [rsp+48h] [rbp-2D0h] BYREF
  int v21; // [rsp+4Ch] [rbp-2CCh] BYREF
  _BYTE v22[8]; // [rsp+50h] [rbp-2C8h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-2C0h]
  FILETIME FileTime2; // [rsp+60h] [rbp-2B8h] BYREF
  BSTR v25; // [rsp+68h] [rbp-2B0h]
  void *v26; // [rsp+70h] [rbp-2A8h] BYREF
  struct _FILETIME v27; // [rsp+78h] [rbp-2A0h] BYREF
  FILETIME v28; // [rsp+80h] [rbp-298h] BYREF
  FILETIME FileTime1; // [rsp+88h] [rbp-290h] BYREF
  _QWORD v30[3]; // [rsp+A8h] [rbp-270h] BYREF
  int v31; // [rsp+C0h] [rbp-258h]
  int v32; // [rsp+C4h] [rbp-254h]
  int v33; // [rsp+C8h] [rbp-250h]
  _DWORD v34[26]; // [rsp+D0h] [rbp-248h] BYREF
  void *Block[3]; // [rsp+138h] [rbp-1E0h] BYREF
  unsigned __int64 v36; // [rsp+150h] [rbp-1C8h]
  OLECHAR psz[4]; // [rsp+160h] [rbp-1B8h] BYREF
  __int64 v38; // [rsp+170h] [rbp-1A8h]
  unsigned __int64 v39; // [rsp+178h] [rbp-1A0h]
  void **v40; // [rsp+190h] [rbp-188h] BYREF
  int v41; // [rsp+198h] [rbp-180h]
  char *v42; // [rsp+240h] [rbp-D8h] BYREF
  __int16 v43; // [rsp+248h] [rbp-D0h]
  __int64 v44; // [rsp+258h] [rbp-C0h]
  __int64 v45; // [rsp+260h] [rbp-B8h]
  __int64 v46; // [rsp+270h] [rbp-A8h]
  char v47; // [rsp+278h] [rbp-A0h]
  FILETIME v48; // [rsp+280h] [rbp-98h] BYREF
  char v49; // [rsp+2C8h] [rbp-50h]

  FileTime1 = (FILETIME)v30;
  v30[0] = L"base\\fs\\fsrm\\service\\modulewrp\\propertybagproxy.cpp";
  v30[1] = L"CPropertyBagProxy::PreSaveCheckAdsCache";
  v30[2] = L"PROPBGPC";
  v31 = 837;
  v32 = 22;
  v33 = 255;
  v34[24] = 0x1000000;
  memset_0(v34, 0, 0x60u);
  CSrmFunctionTracer::CSrmFunctionTracer(&v40, v30, 0);
  if ( *((_DWORD *)this + 54) != 4 )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v40, -2147024809);
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v40);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v40, 0x349u, Hr, 0);
  }
  v41 = 0;
  v26 = 0;
  v6 = (*(__int64 (__fastcall **)(CPropertyBagProxy *, void **))(*(_QWORD *)this + 64LL))(this, &v26);
  v41 = v6;
  if ( v6 < 0 )
  {
    v18 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v40);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v40, v18);
    v19 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v40);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v40, 0x34Du, v19, 0);
  }
  v41 = v6;
  CSrmImpersonationSession::CSrmImpersonationSession((CSrmImpersonationSession *)v22, (char *)v26);
  v45 = 7;
  v44 = 0;
  v43 = 0;
  v7 = (char *)this + 80;
  v42 = (char *)this + 80;
  v46 = 0;
  v47 = 0;
  memset_0(&v48, 0, 0x48u);
  v49 = 0;
  v8 = *(FILETIME *)(*((_QWORD *)this + 11) + 120LL);
  FileTime2 = v8;
  v27 = 0;
  CAdsCacheStream::GetLiveFileTimes((CAdsCacheStream *)&v42, v9, v10, &v27);
  if ( a3 )
  {
    FileTime1 = v27;
    if ( CompareFileTime(&FileTime1, &FileTime2) == 1 )
    {
      (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 56LL))((char *)this + 80, 2105344);
      CSrmResource::LoadStringW(Block, 0x114Fu);
      v11 = *((_QWORD *)this + 2);
      if ( v36 < 8 )
      {
        v12 = Block;
      }
      else
      {
        v12 = (void **)Block[0];
        if ( !Block[0] )
        {
          bstrString = 0;
LABEL_8:
          (*(void (__fastcall **)(char *, BSTR))(v11 + 208))((char *)this + 16, bstrString);
          SysFreeString(bstrString);
          v41 = 1;
          if ( v36 >= 8 )
            operator delete(Block[0]);
          v36 = 7;
          Block[2] = 0;
          LOWORD(Block[0]) = 0;
          goto LABEL_22;
        }
      }
      bstrString = SysAllocString((const OLECHAR *)v12);
      if ( !bstrString )
      {
        pExceptionObject = -2147024882;
        throw (long *)&pExceptionObject;
      }
      goto LABEL_8;
    }
  }
  if ( !CAdsCacheStream::LoadCacheStreamFromDisk((CAdsCacheStream *)&v42, a2, 1) )
    goto LABEL_22;
  CAdsCacheStream::ValidateCacheHeader((CAdsCacheStream *)&v42);
  v28 = v48;
  if ( CompareFileTime(&v28, &FileTime2) != 1 )
    goto LABEL_22;
  (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v7 + 56LL))((char *)this + 80, 2105344);
  CSrmResource::LoadStringW(psz, 0x114Eu);
  v13 = *((_QWORD *)this + 2);
  if ( v39 < 8 )
  {
    v14 = psz;
LABEL_24:
    v25 = SysAllocString(v14);
    if ( !v25 )
    {
      v21 = -2147024882;
      throw (long *)&v21;
    }
    goto LABEL_19;
  }
  v14 = *(OLECHAR **)psz;
  if ( *(_QWORD *)psz )
    goto LABEL_24;
  v25 = 0;
LABEL_19:
  (*(void (__fastcall **)(char *, BSTR))(v13 + 208))((char *)this + 16, v25);
  SysFreeString(v25);
  v41 = 1;
  if ( v39 >= 8 )
    operator delete(*(void **)psz);
  v39 = 7;
  v38 = 0;
  psz[0] = 0;
LABEL_22:
  CAdsCacheStream::~CAdsCacheStream((CAdsCacheStream *)&v42);
  CSrmImpersonationSession::RevertImpersonation((CSrmImpersonationSession *)v22);
  v15 = v41;
  if ( (unsigned int)(v41 + 2147024894) <= 1 )
  {
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 10) + 56LL))((char *)this + 80, 2105344);
    CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v40, 0x8Cu, 0x38Eu, L"File no longer exists");
    v15 = 1;
    goto LABEL_33;
  }
  if ( v41 == -2147024864 )
  {
    (*(void (__fastcall **)(char *, __int64))(*((_QWORD *)this + 10) + 56LL))((char *)this + 80, 2105344);
    CSrmFunctionTracer::Trace((CSrmFunctionTracer *)&v40, 0x8Cu, 0x39Eu, L"Cache is already open in another process");
    v15 = v41;
    goto LABEL_34;
  }
  if ( v41 == -2147024891 && (*(_DWORD *)(*((_QWORD *)this + 11) + 128LL) & 0x4000) != 0 )
  {
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)&v40,
      0x8Cu,
      0x3A9u,
      L"File could not be opened because it is encrypted");
    v15 = -2147200156;
LABEL_33:
    v41 = v15;
  }
LABEL_34:
  v40 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v40);
  return v15;
}

```

## disassembly

```asm
0x1800473c0  mov     r11, rsp
0x1800473c3  push    rbx
0x1800473c4  push    rsi
0x1800473c5  push    rdi
0x1800473c6  push    r12
0x1800473c8  push    r14
0x1800473ca  push    r15
0x1800473cc  sub     rsp, 2E8h
0x1800473d3  mov     rax, cs:__security_cookie
0x1800473da  xor     rax, rsp
0x1800473dd  mov     [rsp+318h+var_48], rax
0x1800473e5  mov     esi, r8d
0x1800473e8  mov     r14d, edx
0x1800473eb  mov     rbx, rcx
0x1800473ee  mov     [rsp+318h+var_2D8], rcx
0x1800473f3  lea     rax, [r11-270h]
0x1800473fa  mov     [r11-290h], rax
0x180047401  lea     rax, aBaseFsFsrmServ_8; "base\\fs\\fsrm\\service\\modulewrp\\pro"...
0x180047408  mov     [r11-270h], rax
0x18004740f  lea     rax, aCpropertybagpr_2; "CPropertyBagProxy::PreSaveCheckAdsCache"
0x180047416  mov     [r11-268h], rax
0x18004741d  lea     rax, aPropbgpc; "PROPBGPC"
0x180047424  mov     [r11-260h], rax
0x18004742b  mov     [rsp+318h+var_258], 345h
0x180047436  mov     [rsp+318h+var_254], 16h
0x180047441  mov     [rsp+318h+var_250], 0FFh
0x18004744c  xor     r15d, r15d
0x18004744f  mov     [rsp+318h+var_1E8], 1000000h
0x18004745a  xor     edx, edx; Val
0x18004745c  lea     r8d, [r15+60h]; Size
0x180047460  lea     rcx, [r11-248h]; void *
0x180047467  call    memset_0
0x18004746c  nop
0x18004746d  xor     r8d, r8d
0x180047470  lea     rdx, [rsp+318h+var_270]
0x180047478  lea     rcx, [rsp+318h+var_188]
0x180047480  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180047485  nop
0x180047486  mov     eax, [rsp+318h+var_180]
0x18004748d  mov     [rsp+318h+var_180], eax
0x180047494  cmp     dword ptr [rbx+0D8h], 4
0x18004749b  jnz     loc_1800478D5
0x1800474a1  mov     [rsp+318h+var_180], r15d
0x1800474a9  mov     [rsp+318h+var_2A8], r15
0x1800474ae  mov     rax, [rbx]
0x1800474b1  lea     rdx, [rsp+318h+var_2A8]
0x1800474b6  mov     rcx, rbx
0x1800474b9  mov     rax, [rax+40h]
0x1800474bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800474c2  mov     [rsp+318h+var_180], eax
0x1800474c9  test    eax, eax
0x1800474cb  js      loc_18004790C
0x1800474d1  mov     [rsp+318h+var_180], eax
0x1800474d8  mov     rdx, [rsp+318h+var_2A8]; void *
0x1800474dd  lea     rcx, [rsp+318h+var_2C8]; this
0x1800474e2  call    ??0CSrmImpersonationSession@@QEAA@PEAX@Z; CSrmImpersonationSession::CSrmImpersonationSession(void *)
0x1800474e7  nop
0x1800474e8  mov     r12d, 7
0x1800474ee  mov     [rsp+318h+var_B8], r12
0x1800474f6  mov     [rsp+318h+var_C0], r15
0x1800474fe  mov     [rsp+318h+var_D0], r15w
0x180047507  lea     rdi, [rbx+50h]
0x18004750b  mov     [rsp+318h+var_D8], rdi
0x180047513  mov     [rsp+318h+var_A8], r15
0x18004751b  mov     [rsp+318h+var_A0], r15b
0x180047523  xor     edx, edx; Val
0x180047525  lea     r8d, [r12+41h]; Size
0x18004752a  lea     rcx, [rsp+318h+var_98]; void *
0x180047532  call    memset_0
0x180047537  mov     [rsp+318h+var_50], r15b
0x18004753f  mov     rax, [rbx+58h]
0x180047543  mov     rcx, [rax+78h]
0x180047547  mov     [rsp+318h+FileTime2.dwLowDateTime], ecx
0x18004754b  shr     rcx, 20h
0x18004754f  mov     [rsp+318h+FileTime2.dwHighDateTime], ecx
0x180047553  mov     qword ptr [rsp+318h+var_2A0.dwLowDateTime], r15
0x180047558  lea     r9, [rsp+318h+var_2A0]; struct _FILETIME *
0x18004755d  lea     rcx, [rsp+318h+var_D8]; this
0x180047565  call    ?GetLiveFileTimes@CAdsCacheStream@@QEBAXPEAU_FILETIME@@00@Z; CAdsCacheStream::GetLiveFileTimes(_FILETIME *,_FILETIME *,_FILETIME *)
0x18004756a  test    esi, esi
0x18004756c  jz      loc_180047663
0x180047572  mov     rax, qword ptr [rsp+318h+var_2A0.dwLowDateTime]
0x180047577  mov     qword ptr [rsp+318h+FileTime1.dwLowDateTime], rax
0x18004757f  lea     rdx, [rsp+318h+FileTime2]; lpFileTime2
0x180047584  lea     rcx, [rsp+318h+FileTime1]; lpFileTime1
0x18004758c  call    cs:__imp_CompareFileTime
0x180047592  cmp     eax, 1
0x180047595  jnz     loc_180047663
0x18004759b  mov     rax, [rdi]
0x18004759e  mov     edx, 202000h
0x1800475a3  mov     rcx, rdi
0x1800475a6  mov     rax, [rax+38h]
0x1800475aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475af  mov     edx, 114Fh; uID
0x1800475b4  lea     rcx, [rsp+318h+Block]; void *
0x1800475bc  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x1800475c1  nop
0x1800475c2  mov     rsi, [rbx+10h]
0x1800475c6  cmp     [rsp+318h+var_1C8], 8
0x1800475cf  jb      short loc_180047645
0x1800475d1  mov     rcx, [rsp+318h+Block]
0x1800475d9  test    rcx, rcx
0x1800475dc  jnz     short loc_18004764D
0x1800475de  mov     [rsp+318h+bstrString], r15
0x1800475e3  mov     rdx, [rsp+318h+bstrString]
0x1800475e8  lea     rcx, [rbx+10h]
0x1800475ec  mov     rax, [rsi+0D0h]
0x1800475f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475f8  nop
0x1800475f9  mov     rcx, [rsp+318h+bstrString]; bstrString
0x1800475fe  call    cs:__imp_SysFreeString
0x180047604  mov     [rsp+318h+var_180], 1
0x18004760f  cmp     [rsp+318h+var_1C8], 8
0x180047618  jb      short loc_180047627
0x18004761a  mov     rcx, [rsp+318h+Block]; Block
0x180047622  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180047627  mov     [rsp+318h+var_1C8], r12
0x18004762f  mov     [rsp+318h+var_1D0], r15
0x180047637  mov     word ptr [rsp+318h+Block], r15w
0x180047640  jmp     loc_180047775
0x180047645  lea     rcx, [rsp+318h+Block]; psz
0x18004764d  call    cs:__imp_SysAllocString
0x180047653  mov     [rsp+318h+bstrString], rax
0x180047658  test    rax, rax
0x18004765b  jz      loc_18004794E
0x180047661  jmp     short loc_1800475E3
0x180047663  mov     r8b, 1; bool
0x180047666  mov     edx, r14d; unsigned int
0x180047669  lea     rcx, [rsp+318h+var_D8]; this
0x180047671  call    ?LoadCacheStreamFromDisk@CAdsCacheStream@@QEAA_NK_N@Z; CAdsCacheStream::LoadCacheStreamFromDisk(ulong,bool)
0x180047676  test    al, al
0x180047678  jz      loc_180047775
0x18004767e  lea     rcx, [rsp+318h+var_D8]; this
0x180047686  call    ?ValidateCacheHeader@CAdsCacheStream@@QEAAXXZ; CAdsCacheStream::ValidateCacheHeader(void)
0x18004768b  mov     eax, dword ptr [rsp+318h+var_98]
0x180047692  mov     [rsp+318h+var_298.dwLowDateTime], eax
0x180047699  mov     rax, [rsp+318h+var_98]
0x1800476a1  shr     rax, 20h
0x1800476a5  mov     [rsp+318h+var_298.dwHighDateTime], eax
0x1800476ac  lea     rdx, [rsp+318h+FileTime2]; lpFileTime2
0x1800476b1  lea     rcx, [rsp+318h+var_298]; lpFileTime1
0x1800476b9  call    cs:__imp_CompareFileTime
0x1800476bf  cmp     eax, 1
0x1800476c2  jnz     loc_180047775
0x1800476c8  mov     rax, [rdi]
0x1800476cb  mov     edx, 202000h
0x1800476d0  mov     rcx, rdi
0x1800476d3  mov     rax, [rax+38h]
0x1800476d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476dc  mov     edx, 114Eh; uID
0x1800476e1  lea     rcx, [rsp+318h+psz]; void *
0x1800476e9  call    ?LoadStringW@CSrmResource@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; CSrmResource::LoadStringW(uint)
0x1800476ee  nop
0x1800476ef  mov     rsi, [rbx+10h]
0x1800476f3  cmp     [rsp+318h+var_1A0], 8
0x1800476fc  jb      loc_180047790
0x180047702  mov     rcx, qword ptr [rsp+318h+psz]
0x18004770a  test    rcx, rcx
0x18004770d  jnz     loc_180047798
0x180047713  mov     [rsp+318h+var_2B0], r15
0x180047718  mov     rdx, [rsp+318h+var_2B0]
0x18004771d  lea     rcx, [rbx+10h]
0x180047721  mov     rax, [rsi+0D0h]
0x180047728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004772d  nop
0x18004772e  mov     rcx, [rsp+318h+var_2B0]; bstrString
0x180047733  call    cs:__imp_SysFreeString
0x180047739  mov     [rsp+318h+var_180], 1
0x180047744  cmp     [rsp+318h+var_1A0], 8
0x18004774d  jb      short loc_18004775C
0x18004774f  mov     rcx, qword ptr [rsp+318h+psz]; Block
0x180047757  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004775c  mov     [rsp+318h+var_1A0], r12
0x180047764  mov     [rsp+318h+var_1A8], r15
0x18004776c  mov     [rsp+318h+psz], r15w
0x180047775  lea     rcx, [rsp+318h+var_D8]; this
0x18004777d  call    ??1CAdsCacheStream@@QEAA@XZ; CAdsCacheStream::~CAdsCacheStream(void)
0x180047782  nop
0x180047783  lea     rcx, [rsp+318h+var_2C8]; this
0x180047788  call    ?RevertImpersonation@CSrmImpersonationSession@@QEAAJXZ; CSrmImpersonationSession::RevertImpersonation(void)
0x18004778d  nop
0x18004778e  jmp     short loc_1800477B6
0x180047790  lea     rcx, [rsp+318h+psz]; psz
0x180047798  call    cs:__imp_SysAllocString
0x18004779e  mov     [rsp+318h+var_2B0], rax
0x1800477a3  test    rax, rax
0x1800477a6  jz      loc_180047968
0x1800477ac  jmp     loc_180047718
0x1800477b1  mov     rbx, [rsp+318h+var_2D8]
0x1800477b6  mov     edi, [rsp+318h+var_180]
0x1800477bd  lea     eax, [rdi+7FF8FFFEh]
0x1800477c3  cmp     eax, 1
0x1800477c6  jbe     loc_180047856
0x1800477cc  cmp     edi, 80070020h
0x1800477d2  jnz     short loc_180047818
0x1800477d4  lea     rcx, [rbx+50h]
0x1800477d8  mov     rax, [rcx]
0x1800477db  mov     edx, 202000h
0x1800477e0  mov     rax, [rax+38h]
0x1800477e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477e9  lea     r9, aCacheIsAlready; "Cache is already open in another proces"...
0x1800477f0  mov     edx, 8Ch; unsigned int
0x1800477f5  mov     r8d, 39Eh; unsigned int
0x1800477fb  lea     rcx, [rsp+318h+var_188]; this
0x180047803  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180047808  mov     edi, [rsp+318h+var_180]
0x18004780f  jmp     loc_180047896
0x180047814  jmp     short loc_1800477B1
0x180047816  jmp     short loc_1800477B1
0x180047818  cmp     edi, 80070005h
0x18004781e  jnz     short loc_180047896
0x180047820  mov     rax, [rbx+58h]
0x180047824  test    dword ptr [rax+80h], 4000h
0x18004782e  jz      short loc_180047896
0x180047830  lea     r9, aFileCouldNotBe; "File could not be opened because it is "...
0x180047837  mov     edx, 8Ch; unsigned int
0x18004783c  mov     r8d, 3A9h; unsigned int
0x180047842  lea     rcx, [rsp+318h+var_188]; this
0x18004784a  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18004784f  mov     edi, 80045364h
0x180047854  jmp     short loc_18004788F
0x180047856  lea     rcx, [rbx+50h]
0x18004785a  mov     rax, [rcx]
0x18004785d  mov     edx, 202000h
0x180047862  mov     rax, [rax+38h]
0x180047866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004786b  lea     r9, aFileNoLongerEx; "File no longer exists"
0x180047872  mov     edx, 8Ch; unsigned int
0x180047877  mov     r8d, 38Eh; unsigned int
0x18004787d  lea     rcx, [rsp+318h+var_188]; this
0x180047885  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x18004788a  mov     edi, 1
0x18004788f  mov     [rsp+318h+var_180], edi
0x180047896  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18004789d  mov     [rsp+318h+var_188], rax
0x1800478a5  lea     rcx, [rsp+318h+var_188]; this
0x1800478ad  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x1800478b2  mov     eax, edi
0x1800478b4  mov     rcx, [rsp+318h+var_48]
0x1800478bc  xor     rcx, rsp; StackCookie
0x1800478bf  call    __security_check_cookie
0x1800478c4  add     rsp, 2E8h
0x1800478cb  pop     r15
0x1800478cd  pop     r14
0x1800478cf  pop     r12
0x1800478d1  pop     rdi
0x1800478d2  pop     rsi
0x1800478d3  pop     rbx
0x1800478d4  retn
0x1800478d5  mov     edx, 80070057h; int
0x1800478da  lea     rcx, [rsp+318h+var_188]; this
0x1800478e2  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x1800478e7  lea     rcx, [rsp+318h+var_188]; this
0x1800478ef  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800478f4  mov     r8d, eax; char
0x1800478f7  xor     r9d, r9d; unsigned __int16 *
0x1800478fa  mov     edx, 349h; unsigned int
0x1800478ff  lea     rcx, [rsp+318h+var_188]; this
0x180047907  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004790c  lea     rcx, [rsp+318h+var_188]; this
0x180047914  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180047919  mov     edx, eax; int
0x18004791b  lea     rcx, [rsp+318h+var_188]; this
0x180047923  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x180047928  lea     rcx, [rsp+318h+var_188]; this
0x180047930  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x180047935  mov     r8d, eax; char
0x180047938  xor     r9d, r9d; unsigned __int16 *
0x18004793b  mov     edx, 34Dh; unsigned int
0x180047940  lea     rcx, [rsp+318h+var_188]; this
0x180047948  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18004794e  mov     [rsp+318h+pExceptionObject], 8007000Eh
0x180047956  lea     rdx, _TI1J; pThrowInfo
0x18004795d  lea     rcx, [rsp+318h+pExceptionObject]; pExceptionObject
0x180047962  call    _CxxThrowException_0
0x180047968  mov     [rsp+318h+var_2CC], 8007000Eh
0x180047970  lea     rdx, _TI1J; pThrowInfo
0x180047977  lea     rcx, [rsp+318h+var_2CC]; pExceptionObject
0x18004797c  call    _CxxThrowException_0
```
