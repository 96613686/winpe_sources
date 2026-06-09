# CSrmRegistryKey::GetValue(ushort const *,ushort * *,bool,bool *)

- ea: `0x1800762f0`
- end: `0x1800766d3`
- name: `?GetValue@CSrmRegistryKey@@QEAA_NPEBGPEAPEAG_NPEA_N@Z`
- size: `995`
- prototype: `bool(CSrmRegistryKey *__hidden this, const unsigned __int16 *, unsigned __int16 **, bool, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0x180014c40`
- `0x1800b0298`

## callees

- `0x18000ac44`
- `0x18000ad14`
- `0x18006fe68`
- `0x18006febc`
- `0x1800700b8`
- `0x18007424c`
- `0x180074a04`
- `0x1800762f0`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800764ea`
- `ole32!CoTaskMemFree` at `0x1800764ea`
- `ADVAPI32!RegQueryValueExW` at `0x1800763d0`
- `ADVAPI32!RegQueryValueExW` at `0x18007649e`
- `ADVAPI32!RegQueryValueExW` at `0x1800763d0`
- `ADVAPI32!RegQueryValueExW` at `0x18007649e`

## string_xrefs

- `0x18007632e`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18007658c`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18007661c`: `base\fs\fsrm\utilities\registry\srmreg.cpp`
- `0x18007633a`: `CSrmRegistryKey::GetValue`
- `0x18007657e`: `CSrmRegistryKey::GetValue`
- `0x18007660e`: `CSrmRegistryKey::GetValue`
- `0x180076688`: `CSrmRegistryKey::GetValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
char __fastcall CSrmRegistryKey::GetValue(HKEY *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  int v6; // ebx
  DWORD v8; // esi
  unsigned __int64 v9; // r15
  unsigned __int16 *v10; // rsi
  BYTE *v11; // rax
  signed int v12; // ebx
  DWORD v13; // esi
  DWORD v14; // r14d
  unsigned __int16 *v15; // r15
  HKEY v16; // rdi
  __int64 v17; // rax
  DWORD v18; // esi
  DWORD v19; // r14d
  unsigned __int16 *Buffer; // r15
  HKEY v21; // rdi
  __int64 v22; // rax
  unsigned __int16 *v23; // rbx
  HKEY v24; // rdi
  __int64 v25; // rax
  LPBYTE lpData; // [rsp+20h] [rbp-E0h]
  LPBYTE v27; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD lpcbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v31; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE *v32; // [rsp+68h] [rbp-98h]
  _QWORD v33[3]; // [rsp+70h] [rbp-90h] BYREF
  int v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+8Ch] [rbp-74h]
  int v36; // [rsp+90h] [rbp-70h]
  _BYTE v37[96]; // [rsp+98h] [rbp-68h] BYREF
  int v38; // [rsp+F8h] [rbp-8h]
  _BYTE v39[144]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v40[22]; // [rsp+190h] [rbp+90h] BYREF

  v27 = (LPBYTE)v33;
  v33[0] = L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp";
  v33[1] = L"CSrmRegistryKey::GetValue";
  v33[2] = L"SRMREGSC";
  v34 = 413;
  v35 = 17;
  v36 = 255;
  v38 = 0x1000000;
  memset_0(v37, 0, sizeof(v37));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v40, (const struct CSrmDebugInfo *)v33, 0);
  if ( a3 )
    *a3 = 0;
  Type = 0;
  cbData = 0;
  v6 = RegQueryValueExW(this[1], a2, 0, &Type, 0, &cbData);
  if ( v6 == 2 )
  {
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v40,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"FALSE");
    v40[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v40);
    return 0;
  }
  else
  {
    if ( v6 && v6 != 234 )
    {
      v18 = cbData;
      v19 = Type;
      Buffer = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v21 = this[1];
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v27 = v39;
      v22 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v39,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetValue",
              447,
              17);
      CSrmFunctionTracer::TranslateGenericError(
        v40,
        v22,
        (unsigned int)v6,
        L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
        v21,
        Buffer,
        a2,
        v19,
        v18);
    }
    v8 = Type;
    if ( Type != 1 && Type != 2 )
    {
      v23 = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v24 = this[1];
      v27 = v39;
      v25 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v39,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetValue",
              453,
              17);
      LODWORD(lpData) = v8;
      CSrmFunctionTracer::TranslateGenericError(
        v40,
        v25,
        2147767062LL,
        L"Unexpected type %lu for a string value 0x%08lx(%s),%s",
        lpData,
        v24,
        v23,
        a2);
    }
    v27 = 0;
    v9 = cbData >> 1;
    CSrmAutoPWSZ::Allocate((CSrmAutoPWSZ *)&v27, v9);
    v31 = 0;
    lpcbData = 2 * v9;
    v10 = (unsigned __int16 *)v27;
    LODWORD(v11) = RegQueryValueExW(this[1], a2, 0, &v31, v27, &lpcbData);
    v12 = (int)v11;
    if ( (_DWORD)v11 )
    {
      v13 = lpcbData;
      v14 = v31;
      v15 = CSrmOutputBuffer::GetBuffer((CSrmOutputBuffer *)(this + 2));
      v16 = this[1];
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
      v32 = v39;
      v17 = CSrmDebugInfo::CSrmDebugInfo(
              (__int64)v39,
              (__int64)L"base\\fs\\fsrm\\utilities\\registry\\srmreg.cpp",
              (__int64)L"SRMREGSC",
              (__int64)L"CSrmRegistryKey::GetValue",
              474,
              17);
      CSrmFunctionTracer::TranslateGenericError(
        v40,
        v17,
        (unsigned int)v12,
        L"RegQueryValueExW(0x%08lx(%s),%s,0,[%lx],0,[%lu])",
        v16,
        v15,
        a2,
        v14,
        v13);
    }
    v10[v9] = 0;
    v27 = v11;
    *a3 = v10;
    CSrmFunctionTracerBase::TraceInternalWithFormat(
      (CSrmFunctionTracerBase *)v40,
      L"RETURN",
      0xAAu,
      L"Returning BOOL: %s",
      L"TRUE");
    CoTaskMemFree(0);
    v27 = 0;
    v40[0] = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v40);
    return 1;
  }
}

```

## disassembly

```asm
0x1800762f0  push    rbp
0x1800762f2  push    rbx
0x1800762f3  push    rsi
0x1800762f4  push    rdi
0x1800762f5  push    r12
0x1800762f7  push    r14
0x1800762f9  push    r15
0x1800762fb  lea     rbp, [rsp-150h]
0x180076303  sub     rsp, 250h
0x18007630a  mov     rax, cs:__security_cookie
0x180076311  xor     rax, rsp
0x180076314  mov     [rbp+180h+var_40], rax
0x18007631b  mov     r14, r8
0x18007631e  mov     r12, rdx
0x180076321  mov     rdi, rcx
0x180076324  lea     rax, [rsp+280h+var_210]
0x180076329  mov     [rsp+280h+var_230], rax
0x18007632e  lea     r15, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180076335  mov     [rsp+280h+var_210], r15
0x18007633a  lea     rax, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x180076341  mov     [rsp+280h+var_208], rax
0x180076346  lea     rax, aSrmregsc; "SRMREGSC"
0x18007634d  mov     [rbp+180h+var_200], rax
0x180076351  mov     [rbp+180h+var_1F8], 19Dh
0x180076358  mov     [rbp+180h+var_1F4], 11h
0x18007635f  mov     [rbp+180h+var_1F0], 0FFh
0x180076366  mov     [rbp+180h+var_188], 1000000h
0x18007636d  xor     edx, edx; Val
0x18007636f  lea     r8d, [rdx+60h]; Size
0x180076373  lea     rcx, [rbp+180h+var_1E8]; void *
0x180076377  call    memset_0
0x18007637c  nop
0x18007637d  xor     r8d, r8d
0x180076380  lea     rdx, [rsp+280h+var_210]
0x180076385  lea     rcx, [rbp+180h+var_F0]
0x18007638c  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180076391  nop
0x180076392  test    r14, r14
0x180076395  jz      short loc_18007639E
0x180076397  mov     qword ptr [r14], 0
0x18007639e  mov     [rsp+280h+Type], 0
0x1800763a6  mov     [rsp+280h+cbData], 0
0x1800763ae  lea     rax, [rsp+280h+cbData]
0x1800763b3  mov     [rsp+280h+lpcbData], rax; lpcbData
0x1800763b8  mov     [rsp+280h+lpData], 0; lpData
0x1800763c1  lea     r9, [rsp+280h+Type]; lpType
0x1800763c6  xor     r8d, r8d; lpReserved
0x1800763c9  mov     rdx, r12; lpValueName
0x1800763cc  mov     rcx, [rdi+8]; hKey
0x1800763d0  call    cs:__imp_RegQueryValueExW
0x1800763d6  mov     ebx, eax
0x1800763d8  cmp     eax, 2
0x1800763db  jnz     short loc_18007642B
0x1800763dd  lea     rax, aFalse; "FALSE"
0x1800763e4  mov     [rsp+280h+lpData], rax
0x1800763e9  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1800763f0  mov     r8d, 0AAh; unsigned int
0x1800763f6  lea     rdx, aReturn; "RETURN"
0x1800763fd  lea     rcx, [rbp+180h+var_F0]; this
0x180076404  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180076409  nop
0x18007640a  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180076411  mov     [rbp+180h+var_F0], rax
0x180076418  lea     rcx, [rbp+180h+var_F0]; this
0x18007641f  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180076424  xor     al, al
0x180076426  jmp     loc_18007651E
0x18007642b  test    ebx, ebx
0x18007642d  jz      short loc_18007643B
0x18007642f  cmp     ebx, 0EAh
0x180076435  jnz     loc_1800765CF
0x18007643b  mov     esi, [rsp+280h+Type]
0x18007643f  cmp     esi, 1
0x180076442  jz      short loc_18007644D
0x180076444  cmp     esi, 2
0x180076447  jnz     loc_18007665F
0x18007644d  mov     [rsp+280h+var_230], 0
0x180076456  mov     eax, [rsp+280h+cbData]
0x18007645a  shr     eax, 1
0x18007645c  mov     r15d, eax
0x18007645f  mov     edx, eax; unsigned __int64
0x180076461  lea     rcx, [rsp+280h+var_230]; this
0x180076466  call    ?Allocate@CSrmAutoPWSZ@@QEAAX_K@Z; CSrmAutoPWSZ::Allocate(unsigned __int64)
0x18007646b  mov     [rsp+280h+var_21C], 0
0x180076473  lea     eax, [r15+r15]
0x180076477  mov     [rsp+280h+var_220], eax
0x18007647b  lea     rax, [rsp+280h+var_220]
0x180076480  mov     [rsp+280h+lpcbData], rax; lpcbData
0x180076485  mov     rsi, [rsp+280h+var_230]
0x18007648a  mov     [rsp+280h+lpData], rsi; lpData
0x18007648f  lea     r9, [rsp+280h+var_21C]; lpType
0x180076494  xor     r8d, r8d; lpReserved
0x180076497  mov     rdx, r12; lpValueName
0x18007649a  mov     rcx, [rdi+8]; hKey
0x18007649e  call    cs:__imp_RegQueryValueExW
0x1800764a4  mov     ebx, eax
0x1800764a6  test    eax, eax
0x1800764a8  jnz     loc_18007653F
0x1800764ae  mov     [rsi+r15*2], ax
0x1800764b3  mov     [rsp+280h+var_230], rax
0x1800764b8  mov     [r14], rsi
0x1800764bb  lea     rax, aTrue_0; "TRUE"
0x1800764c2  mov     [rsp+280h+lpData], rax
0x1800764c7  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x1800764ce  mov     r8d, 0AAh; unsigned int
0x1800764d4  lea     rdx, aReturn; "RETURN"
0x1800764db  lea     rcx, [rbp+180h+var_F0]; this
0x1800764e2  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x1800764e7  nop
0x1800764e8  xor     ecx, ecx; pv
0x1800764ea  call    cs:__imp_CoTaskMemFree
0x1800764f0  mov     [rsp+280h+var_230], 0
0x1800764f9  mov     [rsp+280h+var_230], 0
0x180076502  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180076509  mov     [rbp+180h+var_F0], rax
0x180076510  lea     rcx, [rbp+180h+var_F0]; this
0x180076517  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007651c  mov     al, 1
0x18007651e  mov     rcx, [rbp+180h+var_40]
0x180076525  xor     rcx, rsp; StackCookie
0x180076528  call    __security_check_cookie
0x18007652d  add     rsp, 250h
0x180076534  pop     r15
0x180076536  pop     r14
0x180076538  pop     r12
0x18007653a  pop     rdi
0x18007653b  pop     rsi
0x18007653c  pop     rbx
0x18007653d  pop     rbp
0x18007653e  retn
0x18007653f  mov     esi, [rsp+280h+var_220]
0x180076543  mov     r14d, [rsp+280h+var_21C]
0x180076548  lea     rcx, [rdi+10h]; this
0x18007654c  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180076551  mov     r15, rax
0x180076554  mov     rdi, [rdi+8]
0x180076558  test    ebx, ebx
0x18007655a  jle     short loc_180076565
0x18007655c  movzx   ebx, bx
0x18007655f  or      ebx, 80070000h
0x180076565  lea     rax, [rbp+180h+var_180]
0x180076569  mov     [rsp+280h+var_218], rax
0x18007656e  mov     dword ptr [rsp+280h+lpcbData], 11h
0x180076576  mov     dword ptr [rsp+280h+lpData], 1DAh
0x18007657e  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x180076585  lea     r8, aSrmregsc; "SRMREGSC"
0x18007658c  lea     rdx, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180076593  lea     rcx, [rbp+180h+var_180]
0x180076597  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007659c  nop
0x18007659d  mov     [rsp+280h+var_240], esi
0x1800765a1  mov     dword ptr [rsp+280h+var_248], r14d
0x1800765a6  mov     [rsp+280h+var_250], r12
0x1800765ab  mov     [rsp+280h+lpcbData], r15
0x1800765b0  mov     [rsp+280h+lpData], rdi
0x1800765b5  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x1800765bc  mov     r8d, ebx
0x1800765bf  mov     rdx, rax
0x1800765c2  lea     rcx, [rbp+180h+var_F0]
0x1800765c9  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x1800765cf  mov     esi, [rsp+280h+cbData]
0x1800765d3  mov     r14d, [rsp+280h+Type]
0x1800765d8  lea     rcx, [rdi+10h]; this
0x1800765dc  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x1800765e1  mov     r15, rax
0x1800765e4  mov     rdi, [rdi+8]
0x1800765e8  test    ebx, ebx
0x1800765ea  jle     short loc_1800765F5
0x1800765ec  movzx   ebx, bx
0x1800765ef  or      ebx, 80070000h
0x1800765f5  lea     rax, [rbp+180h+var_180]
0x1800765f9  mov     [rsp+280h+var_230], rax
0x1800765fe  mov     dword ptr [rsp+280h+lpcbData], 11h
0x180076606  mov     dword ptr [rsp+280h+lpData], 1BFh
0x18007660e  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x180076615  lea     r8, aSrmregsc; "SRMREGSC"
0x18007661c  lea     rdx, aBaseFsFsrmUtil_16; "base\\fs\\fsrm\\utilities\\registry\\sr"...
0x180076623  lea     rcx, [rbp+180h+var_180]
0x180076627  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x18007662c  nop
0x18007662d  mov     [rsp+280h+var_240], esi
0x180076631  mov     dword ptr [rsp+280h+var_248], r14d
0x180076636  mov     [rsp+280h+var_250], r12
0x18007663b  mov     [rsp+280h+lpcbData], r15
0x180076640  mov     [rsp+280h+lpData], rdi
0x180076645  lea     r9, aRegqueryvaluee; "RegQueryValueExW(0x%08lx(%s),%s,0,[%lx]"...
0x18007664c  mov     r8d, ebx
0x18007664f  mov     rdx, rax
0x180076652  lea     rcx, [rbp+180h+var_F0]
0x180076659  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
0x18007665f  lea     rcx, [rdi+10h]; this
0x180076663  call    ?GetBuffer@CSrmOutputBuffer@@QEAAPEAGXZ; CSrmOutputBuffer::GetBuffer(void)
0x180076668  mov     rbx, rax
0x18007666b  mov     rdi, [rdi+8]
0x18007666f  lea     rax, [rbp+180h+var_180]
0x180076673  mov     [rsp+280h+var_230], rax
0x180076678  mov     dword ptr [rsp+280h+lpcbData], 11h
0x180076680  mov     dword ptr [rsp+280h+lpData], 1C5h
0x180076688  lea     r9, aCsrmregistryke; "CSrmRegistryKey::GetValue"
0x18007668f  lea     r8, aSrmregsc; "SRMREGSC"
0x180076696  mov     rdx, r15
0x180076699  lea     rcx, [rbp+180h+var_180]
0x18007669d  call    ??0CSrmDebugInfo@@QEAA@PEBG00KKW4_SRMDBG_SEV_ENUM@@@Z; CSrmDebugInfo::CSrmDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_SRMDBG_SEV_ENUM)
0x1800766a2  nop
0x1800766a3  mov     [rsp+280h+var_248], r12
0x1800766a8  mov     [rsp+280h+var_250], rbx
0x1800766ad  mov     [rsp+280h+lpcbData], rdi
0x1800766b2  mov     dword ptr [rsp+280h+lpData], esi
0x1800766b6  lea     r9, aUnexpectedType; "Unexpected type %lu for a string value "...
0x1800766bd  mov     r8d, 80045316h
0x1800766c3  mov     rdx, rax
0x1800766c6  lea     rcx, [rbp+180h+var_F0]
0x1800766cd  call    ?TranslateGenericError@CSrmFunctionTracer@@QEAAXUCSrmDebugInfo@@JPEBGZZ; CSrmFunctionTracer::TranslateGenericError(CSrmDebugInfo,long,ushort const *,...)
```
