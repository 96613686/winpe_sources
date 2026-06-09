# InitializeTracing(void)

- ea: `0x18000574c`
- end: `0x1800059a2`
- name: `?InitializeTracing@@YAJXZ`
- size: `598`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800052a0`

## callees

- `0x18000574c`
- `0x18000b144`
- `0x1800103e0`
- `0x180010e38`
- `0x1800128b0`
- `0x18001d3a0`

## import_xrefs

- `wbemcomn!?Start@CTraceSessionControl@@SAKPEBU_GUID@@PEAVCWMITraceSettings@@@Z` at `0x18000593f`
- `wbemcomn!?Start@CTraceSessionControl@@SAKPEBU_GUID@@PEAVCWMITraceSettings@@@Z` at `0x18000593f`
- `wbemcomn!?SetDefaultValues@CWMITraceSettings@@QEAAKXZ` at `0x180005901`
- `wbemcomn!?SetDefaultValues@CWMITraceSettings@@QEAAKXZ` at `0x180005901`
- `wbemcomn!??0CWMITraceSettings@@QEAA@XZ` at `0x180005895`
- `wbemcomn!??0CWMITraceSettings@@QEAA@XZ` at `0x180005895`
- `wbemcomn!?HasToBeEnabled@CTraceSessionControl@@QEAA_NXZ` at `0x180005870`
- `wbemcomn!?HasToBeEnabled@CTraceSessionControl@@QEAA_NXZ` at `0x180005870`
- `wbemcomn!?Initialize@CTraceSessionControl@@QEAAKPEBG@Z` at `0x1800057c7`
- `wbemcomn!?Initialize@CTraceSessionControl@@QEAAKPEBG@Z` at `0x1800057c7`
- `wbemcomn!SetWMITraceSession` at `0x1800057da`
- `wbemcomn!SetWMITraceSession` at `0x1800057da`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800057a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800058c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800058f8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005956`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005973`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800057a5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800058c2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800058f8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005956`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180005973`
- `wbemcomn!GetMemLogObject` at `0x180005795`
- `wbemcomn!GetMemLogObject` at `0x1800058b2`
- `wbemcomn!GetMemLogObject` at `0x1800058ed`
- `wbemcomn!GetMemLogObject` at `0x18000590d`
- `wbemcomn!GetMemLogObject` at `0x18000594b`
- `wbemcomn!GetMemLogObject` at `0x180005968`
- `wbemcomn!GetMemLogObject` at `0x180005795`
- `wbemcomn!GetMemLogObject` at `0x1800058b2`
- `wbemcomn!GetMemLogObject` at `0x1800058ed`
- `wbemcomn!GetMemLogObject` at `0x18000590d`
- `wbemcomn!GetMemLogObject` at `0x18000594b`
- `wbemcomn!GetMemLogObject` at `0x180005968`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005771`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005883`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005771`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180005883`
- `wbemcomn!?ReadFromRegistry@CWMITraceSettings@@QEAAKPEBG@Z` at `0x1800058e1`
- `wbemcomn!?ReadFromRegistry@CWMITraceSettings@@QEAAKPEBG@Z` at `0x1800058e1`

## pseudocode

```c
__int64 InitializeTracing(void)
{
  CTraceSessionControl *v0; // rax
  CTraceSessionControl *v1; // rbx
  CMemoryLog *v2; // rax
  unsigned int v3; // ebx
  unsigned int v4; // edi
  CWMITraceSettings *v5; // rax
  struct CWMITraceSettings *v6; // rbx
  CMemoryLog *v7; // rax
  unsigned int v8; // edi
  CMemoryLog *v9; // rax
  unsigned int v10; // edi
  CMemoryLog *v11; // rax
  unsigned int v12; // edx
  unsigned int v13; // ebx
  CMemoryLog *MemLogObject; // rax
  CWMITraceSettings *v16; // [rsp+20h] [rbp-30h] BYREF
  CTraceSessionControl *v17; // [rsp+28h] [rbp-28h] BYREF
  struct _GUID v18; // [rsp+30h] [rbp-20h] BYREF

  v0 = (CTraceSessionControl *)CWin32DefaultArena::WbemMemAlloc(0x802u);
  v1 = v0;
  v17 = v0;
  if ( v0 )
  {
    *(_BYTE *)v0 = 0;
    *((_WORD *)v0 + 1) = 0;
  }
  else
  {
    v1 = 0;
  }
  if ( v1 )
  {
    std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(&v17, (__int64)v1);
    v4 = CTraceSessionControl::Initialize(v1, L"Software\\Microsoft\\WBEM\\Tracing\\WMI");
    if ( v4 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v4);
      goto LABEL_22;
    }
    SetWMITraceSession(v1);
    std::unique_ptr<CTraceSessionControl>::release(&v17);
    qword_1800329D0 = 0;
    WPP_MAIN_CB = (__int64)&qword_1800329E8;
    qword_1800329D8 = 513;
    qword_1800329F8 = 0;
    qword_1800329E8 = 0;
    qword_180032A00 = 513;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WMI_Tracing_Guid;
    qword_180032A18 = (__int64)WPP_ThisDir_CTLGUID_WMI_Tracing_Client_Operations_Info_Guid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
    g_bTracing_Initialized = 1;
    if ( *(_BYTE *)v1 || !CTraceSessionControl::HasToBeEnabled(v1) )
      goto LABEL_22;
    v5 = (CWMITraceSettings *)CWin32DefaultArena::WbemMemAlloc(0x10A8u);
    v16 = v5;
    if ( v5 )
      v5 = CWMITraceSettings::CWMITraceSettings(v5);
    std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(&v16, (__int64)v5);
    v6 = v16;
    if ( !v16 )
    {
      v7 = GetMemLogObject();
      v3 = -2147217402;
      CMemoryLog::Write(v7, -2147217402);
      std::unique_ptr<CTraceSessionControl>::~unique_ptr<CTraceSessionControl>((void **)&v16);
LABEL_23:
      std::unique_ptr<CTraceSessionControl>::~unique_ptr<CTraceSessionControl>((void **)&v17);
      return v3;
    }
    v8 = CWMITraceSettings::ReadFromRegistry(v16, L"Software\\Microsoft\\WBEM\\Tracing\\WMI");
    if ( v8 && (v9 = GetMemLogObject(), CMemoryLog::Write(v9, v8), (v10 = CWMITraceSettings::SetDefaultValues(v6)) != 0) )
    {
      v11 = GetMemLogObject();
      v12 = v10;
    }
    else
    {
      if ( !*(_BYTE *)v6 )
        goto LABEL_20;
      v18.Data1 = 536261159;
      *(_DWORD *)&v18.Data2 = 1090071719;
      *(_DWORD *)v18.Data4 = 244868762;
      *(_DWORD *)&v18.Data4[4] = 778087085;
      v13 = CTraceSessionControl::Start(&v18, v6);
      if ( !v13 )
        goto LABEL_20;
      v11 = GetMemLogObject();
      v12 = v13;
    }
    CMemoryLog::Write(v11, v12);
LABEL_20:
    std::unique_ptr<CTraceSessionControl>::~unique_ptr<CTraceSessionControl>((void **)&v16);
LABEL_22:
    v3 = 0;
    goto LABEL_23;
  }
  v2 = GetMemLogObject();
  v3 = -2147217402;
  CMemoryLog::Write(v2, -2147217402);
  return v3;
}

```

## disassembly

```asm
0x18000574c  mov     [rsp-8+arg_0], rbx
0x180005751  mov     [rsp-8+arg_8], rdi
0x180005756  push    rbp
0x180005757  mov     rbp, rsp
0x18000575a  sub     rsp, 50h
0x18000575e  mov     rax, cs:__security_cookie
0x180005765  xor     rax, rsp
0x180005768  mov     [rbp+var_10], rax
0x18000576c  mov     ecx, 802h
0x180005771  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180005777  mov     rbx, rax
0x18000577a  mov     [rbp+var_28], rax
0x18000577e  test    rax, rax
0x180005781  jz      short loc_18000578E
0x180005783  mov     byte ptr [rax], 0
0x180005786  xor     eax, eax
0x180005788  mov     [rbx+2], ax
0x18000578c  jmp     short loc_180005790
0x18000578e  xor     ebx, ebx
0x180005790  test    rbx, rbx
0x180005793  jnz     short loc_1800057B0
0x180005795  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000579b  mov     ebx, 80041006h
0x1800057a0  mov     edx, ebx
0x1800057a2  mov     rcx, rax
0x1800057a5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800057ab  jmp     loc_180005984
0x1800057b0  mov     rdx, rbx
0x1800057b3  lea     rcx, [rbp+var_28]
0x1800057b7  call    ??0?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@PEAVCTraceSessionControl@@@Z; std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(CTraceSessionControl *)
0x1800057bc  nop
0x1800057bd  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WBEM\\Tracing\\WMI"
0x1800057c4  mov     rcx, rbx
0x1800057c7  call    cs:__imp_?Initialize@CTraceSessionControl@@QEAAKPEBG@Z; CTraceSessionControl::Initialize(ushort const *)
0x1800057cd  mov     edi, eax
0x1800057cf  test    eax, eax
0x1800057d1  jnz     loc_180005968
0x1800057d7  mov     rcx, rbx
0x1800057da  call    cs:__imp_?SetWMITraceSession@@YAXPEAX@Z; SetWMITraceSession(void *)
0x1800057e0  lea     rcx, [rbp+var_28]
0x1800057e4  call    ?release@?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAAPEAVCTraceSessionControl@@XZ; std::unique_ptr<CTraceSessionControl>::release(void)
0x1800057e9  mov     cs:qword_1800329D0, 0
0x1800057f4  lea     rax, qword_1800329E8
0x1800057fb  mov     cs:WPP_MAIN_CB, rax
0x180005802  mov     cs:qword_1800329D8, 201h
0x18000580d  mov     cs:qword_1800329F8, 0
0x180005818  mov     cs:qword_1800329E8, 0
0x180005823  mov     cs:qword_180032A00, 201h
0x18000582e  lea     rax, WPP_ThisDir_CTLGUID_WMI_Tracing_Guid
0x180005835  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000583c  lea     rax, WPP_ThisDir_CTLGUID_WMI_Tracing_Client_Operations_Info_Guid
0x180005843  mov     cs:qword_180032A18, rax
0x18000584a  lea     rax, WPP_MAIN_CB
0x180005851  mov     cs:WPP_GLOBAL_Control, rax
0x180005858  call    WppInitUm
0x18000585d  mov     cs:?g_bTracing_Initialized@@3_NA, 1; bool g_bTracing_Initialized
0x180005864  cmp     [rbx], dil
0x180005867  jnz     loc_180005979
0x18000586d  mov     rcx, rbx
0x180005870  call    cs:__imp_?HasToBeEnabled@CTraceSessionControl@@QEAA_NXZ; CTraceSessionControl::HasToBeEnabled(void)
0x180005876  test    al, al
0x180005878  jz      loc_180005979
0x18000587e  mov     ecx, 10A8h
0x180005883  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180005889  mov     [rbp+var_30], rax
0x18000588d  test    rax, rax
0x180005890  jz      short loc_18000589C
0x180005892  mov     rcx, rax
0x180005895  call    cs:__imp_??0CWMITraceSettings@@QEAA@XZ; CWMITraceSettings::CWMITraceSettings(void)
0x18000589b  nop
0x18000589c  mov     rdx, rax
0x18000589f  lea     rcx, [rbp+var_30]
0x1800058a3  call    ??0?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@PEAVCTraceSessionControl@@@Z; std::unique_ptr<CTraceSessionControl>::unique_ptr<CTraceSessionControl>(CTraceSessionControl *)
0x1800058a8  nop
0x1800058a9  mov     rbx, [rbp+var_30]
0x1800058ad  test    rbx, rbx
0x1800058b0  jnz     short loc_1800058D7
0x1800058b2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800058b8  mov     ebx, 80041006h
0x1800058bd  mov     edx, ebx
0x1800058bf  mov     rcx, rax
0x1800058c2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800058c8  nop
0x1800058c9  lea     rcx, [rbp+var_30]
0x1800058cd  call    ??1?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@XZ; std::unique_ptr<CTraceSessionControl>::~unique_ptr<CTraceSessionControl>(void)
0x1800058d2  jmp     loc_18000597B
0x1800058d7  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WBEM\\Tracing\\WMI"
0x1800058de  mov     rcx, rbx
0x1800058e1  call    cs:__imp_?ReadFromRegistry@CWMITraceSettings@@QEAAKPEBG@Z; CWMITraceSettings::ReadFromRegistry(ushort const *)
0x1800058e7  mov     edi, eax
0x1800058e9  test    eax, eax
0x1800058eb  jz      short loc_180005917
0x1800058ed  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800058f3  mov     edx, edi
0x1800058f5  mov     rcx, rax
0x1800058f8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800058fe  mov     rcx, rbx
0x180005901  call    cs:__imp_?SetDefaultValues@CWMITraceSettings@@QEAAKXZ; CWMITraceSettings::SetDefaultValues(void)
0x180005907  mov     edi, eax
0x180005909  test    eax, eax
0x18000590b  jz      short loc_180005917
0x18000590d  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180005913  mov     edx, edi
0x180005915  jmp     short loc_180005953
0x180005917  cmp     byte ptr [rbx], 0
0x18000591a  jbe     short loc_18000595D
0x18000591c  mov     [rbp+var_20], 1FF6B227h
0x180005923  mov     [rbp+var_1C], 40F92CA7h
0x18000592a  mov     [rbp+var_18], 0E98669Ah
0x180005931  mov     [rbp+var_14], 2E60AAADh
0x180005938  mov     rdx, rbx
0x18000593b  lea     rcx, [rbp+var_20]
0x18000593f  call    cs:__imp_?Start@CTraceSessionControl@@SAKPEBU_GUID@@PEAVCWMITraceSettings@@@Z; CTraceSessionControl::Start(_GUID const *,CWMITraceSettings *)
0x180005945  mov     ebx, eax
0x180005947  test    eax, eax
0x180005949  jz      short loc_18000595D
0x18000594b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180005951  mov     edx, ebx
0x180005953  mov     rcx, rax
0x180005956  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18000595c  nop
0x18000595d  lea     rcx, [rbp+var_30]
0x180005961  call    ??1?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@XZ; std::unique_ptr<CTraceSessionControl>::~unique_ptr<CTraceSessionControl>(void)
0x180005966  jmp     short loc_180005979
0x180005968  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18000596e  mov     edx, edi
0x180005970  mov     rcx, rax
0x180005973  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180005979  xor     ebx, ebx
0x18000597b  lea     rcx, [rbp+var_28]
0x18000597f  call    ??1?$unique_ptr@VCTraceSessionControl@@U?$default_delete@VCTraceSessionControl@@@std@@@std@@QEAA@XZ; std::unique_ptr<CTraceSessionControl>::~unique_ptr<CTraceSessionControl>(void)
0x180005984  mov     eax, ebx
0x180005986  mov     rcx, [rbp+var_10]
0x18000598a  xor     rcx, rsp; StackCookie
0x18000598d  call    __security_check_cookie
0x180005992  mov     rbx, [rsp+50h+arg_0]
0x180005997  mov     rdi, [rsp+50h+arg_8]
0x18000599c  add     rsp, 50h
0x1800059a0  pop     rbp
0x1800059a1  retn
```
