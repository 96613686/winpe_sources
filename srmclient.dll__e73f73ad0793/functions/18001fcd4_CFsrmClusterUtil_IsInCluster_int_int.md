# CFsrmClusterUtil::IsInCluster(int,int)

- ea: `0x18001fcd4`
- end: `0x18002014a`
- name: `?IsInCluster@CFsrmClusterUtil@@SA_NHH@Z`
- size: `1142`
- prototype: `bool __fastcall(int, int)`
- caller_count: `6`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x18000f98c`
- `0x18000fb7c`
- `0x18000fd74`
- `0x1800101e8`
- `0x1800106e0`
- `0x18005162c`

## callees

- `0x180006a1c`
- `0x18001fcd4`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x180073d04`
- `0x180074048`
- `0x18007424c`
- `0x180074a04`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `KERNEL32!Sleep` at `0x18001fe06`
- `KERNEL32!Sleep` at `0x18001fe06`
- `CLUSAPI!GetNodeClusterState` at `0x18001fd75`
- `CLUSAPI!GetNodeClusterState` at `0x18001fd75`

## string_xrefs

- `0x18001fd07`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001fdab`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001fe2a`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001fe85`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x18001fee2`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x1800200d7`: `base\fs\fsrm\service\globalstore\clusterutil.cpp`
- `0x180020000`: `GetNodeClusterState indicated that cluster service is not running...`
- `0x1800200a2`: `Cluster service not running`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall CFsrmClusterUtil::IsInCluster(int a1, int a2)
{
  char v4; // si
  int v5; // r15d
  DWORD NodeClusterState; // eax
  signed int v7; // edi
  int v8; // ebx
  DWORD v9; // ebx
  const wchar_t *v10; // rax
  __int64 v12; // rax
  unsigned int Hr; // eax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+20h] [rbp-E0h]
  DWORD pdwClusterState; // [rsp+48h] [rbp-B8h] BYREF
  const wchar_t *v19; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v20; // [rsp+58h] [rbp-A8h]
  const wchar_t *v21; // [rsp+60h] [rbp-A0h]
  __int64 v22; // [rsp+68h] [rbp-98h]
  int v23; // [rsp+70h] [rbp-90h]
  _BYTE v24[96]; // [rsp+78h] [rbp-88h] BYREF
  int v25; // [rsp+D8h] [rbp-28h]
  _QWORD v26[4]; // [rsp+E0h] [rbp-20h] BYREF
  int v27; // [rsp+100h] [rbp+0h]
  _BYTE v28[96]; // [rsp+108h] [rbp+8h] BYREF
  int v29; // [rsp+168h] [rbp+68h]
  void **v30; // [rsp+170h] [rbp+70h] BYREF
  int v31; // [rsp+178h] [rbp+78h]

  v26[0] = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
  v26[1] = L"CFsrmClusterUtil::IsInCluster";
  v26[2] = L"CLUSUTLC";
  v26[3] = 51;
  v27 = 255;
  v29 = 0x1000000;
  v4 = 1;
  memset_0(v28, 0, sizeof(v28));
  CSrmFunctionTracer::CSrmFunctionTracer(
    (__int64)&v30,
    (const struct CSrmDebugInfo *)v26,
    (__int64)L"CFsrmClusterUtil::IsInCluster");
  v5 = 10;
  while ( 1 )
  {
    pdwClusterState = 0;
    NodeClusterState = GetNodeClusterState(0, &pdwClusterState);
    v7 = NodeClusterState;
    if ( !NodeClusterState )
      break;
    v23 = 255;
    v25 = 0x1000000;
    if ( NodeClusterState == 70 )
    {
      v19 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
      v20 = L"CFsrmClusterUtil::IsInCluster";
      v21 = L"CLUSUTLC";
      v22 = 74;
      memset_0(v24, 0, sizeof(v24));
      CSrmFunctionTracer::Trace(
        &v30,
        &v19,
        L"GetNodeClusterState(NULL, &dwClusterState) failed with Win32 Status ERROR_SHARING_PAUSED - fake not-running state");
      v9 = 3;
      pdwClusterState = 3;
      goto LABEL_12;
    }
    v8 = v31;
    v19 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
    v20 = L"CFsrmClusterUtil::IsInCluster";
    v21 = L"CLUSUTLC";
    v22 = 80;
    memset_0(v24, 0, sizeof(v24));
    LODWORD(v16) = v8;
    CSrmFunctionTracer::Trace(
      &v30,
      &v19,
      L"GetNodeClusterState(NULL, &dwClusterState) failed #%d with hr=0x%08lx",
      (unsigned int)v5--,
      v16);
    if ( v5 <= 0 )
    {
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
      v31 = v7;
      if ( !a1 )
      {
        CSrmDebugInfo::CSrmDebugInfo(
          (__int64)&v19,
          (__int64)L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp",
          (__int64)L"CLUSUTLC",
          (__int64)L"CFsrmClusterUtil::IsInCluster",
          99,
          0);
        Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v30);
        CSrmFunctionTracer::TranslateGenericError(&v30, v14, Hr, L"GetNodeClusterState(NULL, &dwClusterState)");
      }
      v19 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
      v20 = L"CFsrmClusterUtil::IsInCluster";
      v21 = L"CLUSUTLC";
      v22 = 94;
      v23 = 255;
      v25 = 0x1000000;
      memset_0(v24, 0, sizeof(v24));
      CSrmFunctionTracer::Trace(
        &v30,
        &v19,
        L"GetNodeClusterState(NULL, &dwClusterState) failed with hr=0x%08lx",
        (unsigned int)v7);
      goto LABEL_17;
    }
    Sleep(0x3E8u);
  }
  v9 = pdwClusterState;
LABEL_12:
  if ( v9 >= 2 )
  {
    if ( v9 != 3 )
    {
      if ( v9 == 19 )
      {
        v10 = L"TRUE";
      }
      else
      {
        if ( !a1 )
        {
          v15 = CSrmDebugInfo::CSrmDebugInfo(
                  (__int64)&v19,
                  (__int64)L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp",
                  (__int64)L"CLUSUTLC",
                  (__int64)L"CFsrmClusterUtil::IsInCluster",
                  133,
                  0);
          LODWORD(v17) = v9;
          CSrmFunctionTracer::Throw(&v30, v15, 2147767062LL, L"- Unexpected cluster state [%d]", v17);
        }
        v31 = -2147200234;
        v19 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
        v20 = L"CFsrmClusterUtil::IsInCluster";
        v21 = L"CLUSUTLC";
        v22 = 128;
        v23 = 255;
        v25 = 0x1000000;
        memset_0(v24, 0, sizeof(v24));
        CSrmFunctionTracer::Trace(&v30, &v19, L"- Unexpected cluster state [%d]", v9);
LABEL_17:
        v4 = 0;
        v10 = L"FALSE";
      }
      CSrmFunctionTracerBase::TraceInternalWithFormat(
        (CSrmFunctionTracerBase *)&v30,
        L"RETURN",
        0xAAu,
        L"Returning BOOL: %s",
        v10);
      v30 = &CSrmFunctionTracer::`vftable';
      CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v30);
      return v4;
    }
    v19 = L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp";
    v20 = L"CFsrmClusterUtil::IsInCluster";
    v21 = L"CLUSUTLC";
    v22 = 107;
    v23 = 255;
    v25 = 0x1000000;
    memset_0(v24, 0, sizeof(v24));
    CSrmFunctionTracer::Trace(&v30, &v19, L"GetNodeClusterState indicated that cluster service is not running...");
    if ( !a1 && a2 )
    {
      v12 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)&v19,
              (__int64)L"base\\fs\\fsrm\\service\\globalstore\\clusterutil.cpp",
              (__int64)L"CLUSUTLC",
              (__int64)L"CFsrmClusterUtil::IsInCluster",
              110,
              0);
      CSrmFunctionTracer::Throw(&v30, v12, 2147767086LL, L"Cluster service not running");
    }
  }
  CSrmFunctionTracerBase::TraceInternalWithFormat(
    (CSrmFunctionTracerBase *)&v30,
    L"RETURN",
    0xAAu,
    L"Returning BOOL: %s",
    L"FALSE");
  v30 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v30);
  return 0;
}

```

## disassembly

```asm
0x18001fcd4  push    rbp
0x18001fcd6  push    rbx
0x18001fcd7  push    rsi
0x18001fcd8  push    rdi
0x18001fcd9  push    r12
0x18001fcdb  push    r13
0x18001fcdd  push    r14
0x18001fcdf  push    r15
0x18001fce1  lea     rbp, [rsp-138h]
0x18001fce9  sub     rsp, 238h
0x18001fcf0  mov     rax, cs:__security_cookie
0x18001fcf7  xor     rax, rsp
0x18001fcfa  mov     [rbp+170h+var_50], rax
0x18001fd01  mov     r12d, edx
0x18001fd04  mov     r14d, ecx
0x18001fd07  lea     rax, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001fd0e  mov     [rbp+170h+var_190], rax
0x18001fd12  lea     rbx, aCfsrmclusterut_13; "CFsrmClusterUtil::IsInCluster"
0x18001fd19  mov     [rbp+170h+var_188], rbx
0x18001fd1d  lea     rax, aClusutlc; "CLUSUTLC"
0x18001fd24  mov     [rbp+170h+var_180], rax
0x18001fd28  mov     [rbp+170h+var_178], 33h ; '3'
0x18001fd30  xor     r13d, r13d
0x18001fd33  mov     [rbp+170h+var_170], 0FFh
0x18001fd3a  mov     [rbp+170h+var_108], 1000000h
0x18001fd41  lea     esi, [r13+1]
0x18001fd45  xor     edx, edx; Val
0x18001fd47  lea     r8d, [r13+60h]; Size
0x18001fd4b  lea     rcx, [rbp+170h+var_168]; void *
0x18001fd4f  call    memset_0
0x18001fd54  mov     r8, rbx
0x18001fd57  lea     rdx, [rbp+170h+var_190]
0x18001fd5b  lea     rcx, [rbp+170h+var_100]
0x18001fd5f  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18001fd64  nop
0x18001fd65  lea     r15d, [r13+0Ah]
0x18001fd69  mov     [rsp+270h+pdwClusterState], r13d
0x18001fd6e  lea     rdx, [rsp+270h+pdwClusterState]; pdwClusterState
0x18001fd73  xor     ecx, ecx; lpszNodeName
0x18001fd75  call    cs:__imp_GetNodeClusterState
0x18001fd7b  mov     edi, eax
0x18001fd7d  test    eax, eax
0x18001fd7f  jz      loc_18001FED7
0x18001fd85  mov     [rsp+270h+var_200], 0FFh
0x18001fd8d  mov     [rbp+170h+var_198], 1000000h
0x18001fd94  xor     edx, edx; Val
0x18001fd96  lea     r8d, [rdx+60h]; Size
0x18001fd9a  lea     rcx, [rsp+270h+var_1F8]; void *
0x18001fd9f  cmp     eax, 46h ; 'F'
0x18001fda2  jz      loc_18001FE85
0x18001fda8  mov     ebx, [rbp+170h+var_F8]
0x18001fdab  lea     rax, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001fdb2  mov     [rsp+270h+var_220], rax
0x18001fdb7  lea     rax, aCfsrmclusterut_13; "CFsrmClusterUtil::IsInCluster"
0x18001fdbe  mov     [rsp+270h+var_218], rax
0x18001fdc3  lea     rax, aClusutlc; "CLUSUTLC"
0x18001fdca  mov     [rsp+270h+var_210], rax
0x18001fdcf  mov     [rsp+270h+var_208], 50h ; 'P'
0x18001fdd8  call    memset_0
0x18001fddd  mov     dword ptr [rsp+270h+var_250], ebx
0x18001fde1  mov     r9d, r15d
0x18001fde4  lea     r8, aGetnodecluster_1; "GetNodeClusterState(NULL, &dwClusterSta"...
0x18001fdeb  lea     rdx, [rsp+270h+var_220]
0x18001fdf0  lea     rcx, [rbp+170h+var_100]
0x18001fdf4  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001fdf9  sub     r15d, esi
0x18001fdfc  test    r15d, r15d
0x18001fdff  jle     short loc_18001FE11
0x18001fe01  mov     ecx, 3E8h; dwMilliseconds
0x18001fe06  call    cs:__imp_Sleep
0x18001fe0c  jmp     loc_18001FD69
0x18001fe11  test    edi, edi
0x18001fe13  jle     short loc_18001FE1E
0x18001fe15  movzx   edi, di
0x18001fe18  or      edi, 80070000h
0x18001fe1e  mov     [rbp+170h+var_F8], edi
0x18001fe21  test    r14d, r14d
0x18001fe24  jz      loc_1800200BC
0x18001fe2a  lea     rax, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001fe31  mov     [rsp+270h+var_220], rax
0x18001fe36  lea     rax, aCfsrmclusterut_13; "CFsrmClusterUtil::IsInCluster"
0x18001fe3d  mov     [rsp+270h+var_218], rax
0x18001fe42  lea     rax, aClusutlc; "CLUSUTLC"
0x18001fe49  mov     [rsp+270h+var_210], rax
0x18001fe4e  mov     [rsp+270h+var_208], 5Eh ; '^'
0x18001fe57  mov     [rsp+270h+var_200], 0FFh
0x18001fe5f  mov     [rbp+170h+var_198], 1000000h
0x18001fe66  xor     edx, edx; Val
0x18001fe68  lea     r8d, [rdx+60h]; Size
0x18001fe6c  lea     rcx, [rsp+270h+var_1F8]; void *
0x18001fe71  call    memset_0
0x18001fe76  mov     r9d, edi
0x18001fe79  lea     r8, aGetnodecluster_3; "GetNodeClusterState(NULL, &dwClusterSta"...
0x18001fe80  jmp     loc_18001FF62
0x18001fe85  lea     r15, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001fe8c  mov     [rsp+270h+var_220], r15
0x18001fe91  lea     rdi, aCfsrmclusterut_13; "CFsrmClusterUtil::IsInCluster"
0x18001fe98  mov     [rsp+270h+var_218], rdi
0x18001fe9d  lea     rax, aClusutlc; "CLUSUTLC"
0x18001fea4  mov     [rsp+270h+var_210], rax
0x18001fea9  mov     [rsp+270h+var_208], 4Ah ; 'J'
0x18001feb2  call    memset_0
0x18001feb7  lea     r8, aGetnodecluster_0; "GetNodeClusterState(NULL, &dwClusterSta"...
0x18001febe  lea     rdx, [rsp+270h+var_220]
0x18001fec3  lea     rcx, [rbp+170h+var_100]
0x18001fec7  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001fecc  mov     ebx, 3
0x18001fed1  mov     [rsp+270h+pdwClusterState], ebx
0x18001fed5  jmp     short loc_18001FEE9
0x18001fed7  mov     ebx, [rsp+270h+pdwClusterState]
0x18001fedb  lea     rdi, aCfsrmclusterut_13; "CFsrmClusterUtil::IsInCluster"
0x18001fee2  lea     r15, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x18001fee9  mov     eax, ebx
0x18001feeb  test    ebx, ebx
0x18001feed  jz      loc_18002001F
0x18001fef3  sub     eax, 1
0x18001fef6  jz      loc_18002001F
0x18001fefc  sub     eax, 2
0x18001feff  jz      loc_18001FFC2
0x18001ff05  cmp     eax, 10h
0x18001ff08  jz      short loc_18001FF7C
0x18001ff0a  test    r14d, r14d
0x18001ff0d  jz      loc_180020108
0x18001ff13  mov     [rbp+170h+var_F8], 80045316h
0x18001ff1a  mov     [rsp+270h+var_220], r15
0x18001ff1f  mov     [rsp+270h+var_218], rdi
0x18001ff24  lea     rax, aClusutlc; "CLUSUTLC"
0x18001ff2b  mov     [rsp+270h+var_210], rax
0x18001ff30  mov     [rsp+270h+var_208], 80h
0x18001ff39  mov     [rsp+270h+var_200], 0FFh
0x18001ff41  mov     [rbp+170h+var_198], 1000000h
0x18001ff48  xor     edx, edx; Val
0x18001ff4a  lea     r8d, [rdx+60h]; Size
0x18001ff4e  lea     rcx, [rsp+270h+var_1F8]; void *
0x18001ff53  call    memset_0
0x18001ff58  mov     r9d, ebx
0x18001ff5b  lea     r8, aUnexpectedClus; "- Unexpected cluster state [%d]"
0x18001ff62  lea     rdx, [rsp+270h+var_220]
0x18001ff67  lea     rcx, [rbp+170h+var_100]
0x18001ff6b  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x18001ff70  mov     sil, r13b
0x18001ff73  lea     rax, aFalse; "FALSE"
0x18001ff7a  jmp     short loc_18001FF83
0x18001ff7c  lea     rax, aTrue_0; "TRUE"
0x18001ff83  mov     [rsp+270h+var_250], rax
0x18001ff88  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x18001ff8f  mov     r8d, 0AAh; unsigned int
0x18001ff95  lea     rdx, aReturn; "RETURN"
0x18001ff9c  lea     rcx, [rbp+170h+var_100]; this
0x18001ffa0  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x18001ffa5  nop
0x18001ffa6  lea     rcx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001ffad  mov     [rbp+170h+var_100], rcx
0x18001ffb1  lea     rcx, [rbp+170h+var_100]; this
0x18001ffb5  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18001ffba  mov     al, sil
0x18001ffbd  jmp     loc_18002005F
0x18001ffc2  mov     [rsp+270h+var_220], r15
0x18001ffc7  mov     [rsp+270h+var_218], rdi
0x18001ffcc  lea     rbx, aClusutlc; "CLUSUTLC"
0x18001ffd3  mov     [rsp+270h+var_210], rbx
0x18001ffd8  mov     [rsp+270h+var_208], 6Bh ; 'k'
0x18001ffe1  mov     [rsp+270h+var_200], 0FFh
0x18001ffe9  mov     [rbp+170h+var_198], 1000000h
0x18001fff0  xor     edx, edx; Val
0x18001fff2  lea     r8d, [rdx+60h]; Size
0x18001fff6  lea     rcx, [rsp+270h+var_1F8]; void *
0x18001fffb  call    memset_0
0x180020000  lea     r8, aGetnodecluster; "GetNodeClusterState indicated that clus"...
0x180020007  lea     rdx, [rsp+270h+var_220]
0x18002000c  lea     rcx, [rbp+170h+var_100]
0x180020010  call    ?Trace@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@PEBGZZ; CSrmFunctionTracer::Trace(CSrmDebugInfo,ushort const *,...)
0x180020015  test    r14d, r14d
0x180020018  jnz     short loc_18002001F
0x18002001a  test    r12d, r12d
0x18002001d  jnz     short loc_180020082
0x18002001f  lea     rax, aFalse; "FALSE"
0x180020026  mov     [rsp+270h+var_250], rax
0x18002002b  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x180020032  mov     r8d, 0AAh; unsigned int
0x180020038  lea     rdx, aReturn; "RETURN"
0x18002003f  lea     rcx, [rbp+170h+var_100]; this
0x180020043  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180020048  nop
0x180020049  lea     rcx, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180020050  mov     [rbp+170h+var_100], rcx
0x180020054  lea     rcx, [rbp+170h+var_100]; this
0x180020058  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18002005d  xor     al, al
0x18002005f  mov     rcx, [rbp+170h+var_50]
0x180020066  xor     rcx, rsp; StackCookie
0x180020069  call    __security_check_cookie
0x18002006e  add     rsp, 238h
0x180020075  pop     r15
0x180020077  pop     r14
0x180020079  pop     r13
0x18002007b  pop     r12
0x18002007d  pop     rdi
0x18002007e  pop     rsi
0x18002007f  pop     rbx
0x180020080  pop     rbp
0x180020081  retn
0x180020082  mov     [rsp+270h+var_248], r13d
0x180020087  mov     dword ptr [rsp+270h+var_250], 6Eh ; 'n'
0x18002008f  mov     r9, rdi
0x180020092  mov     r8, rbx
0x180020095  mov     rdx, r15
0x180020098  lea     rcx, [rsp+270h+var_220]
0x18002009d  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800200a2  lea     r9, aClusterService; "Cluster service not running"
0x1800200a9  mov     r8d, 8004532Eh
0x1800200af  mov     rdx, rax
0x1800200b2  lea     rcx, [rbp+170h+var_100]
0x1800200b6  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
0x1800200bc  mov     [rsp+270h+var_248], r13d
0x1800200c1  mov     dword ptr [rsp+270h+var_250], 63h ; 'c'
0x1800200c9  lea     r9, aCfsrmclusterut_13; "CFsrmClusterUtil::IsInCluster"
0x1800200d0  lea     r8, aClusutlc; "CLUSUTLC"
0x1800200d7  lea     rdx, aBaseFsFsrmServ_40; "base\\fs\\fsrm\\service\\globalstore\\c"...
0x1800200de  lea     rcx, [rsp+270h+var_220]
0x1800200e3  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800200e8  mov     rdx, rax
0x1800200eb  lea     rcx, [rbp+170h+var_100]; this
0x1800200ef  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x1800200f4  mov     r8d, eax
0x1800200f7  lea     r9, aGetnodecluster_2; "GetNodeClusterState(NULL, &dwClusterSta"...
0x1800200fe  lea     rcx, [rbp+170h+var_100]
0x180020102  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x180020108  mov     [rsp+270h+var_248], r13d
0x18002010d  mov     dword ptr [rsp+270h+var_250], 85h
0x180020115  mov     r9, rdi
0x180020118  lea     r8, aClusutlc; "CLUSUTLC"
0x18002011f  mov     rdx, r15
0x180020122  lea     rcx, [rsp+270h+var_220]
0x180020127  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18002012c  mov     dword ptr [rsp+270h+var_250], ebx
0x180020130  lea     r9, aUnexpectedClus; "- Unexpected cluster state [%d]"
0x180020137  mov     r8d, 80045316h
0x18002013d  mov     rdx, rax
0x180020140  lea     rcx, [rbp+170h+var_100]
0x180020144  call    ?Throw@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::Throw(CSrmDebugInfo,long,ushort const *,...)
```
