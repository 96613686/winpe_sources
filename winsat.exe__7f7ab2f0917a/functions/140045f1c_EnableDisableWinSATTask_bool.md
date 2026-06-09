# EnableDisableWinSATTask(bool)

- ea: `0x140045f1c`
- end: `0x140046190`
- name: `?EnableDisableWinSATTask@@YAJ_N@Z`
- size: `628`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14001a54c`

## callees

- `0x14000712c`
- `0x14003ec14`
- `0x140044b74`
- `0x140045f1c`
- `0x14011a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140046060`
- `OLEAUT32!__imp_SysFreeString` at `0x140046154`
- `OLEAUT32!__imp_SysFreeString` at `0x140046168`
- `OLEAUT32!__imp_SysFreeString` at `0x140046060`
- `OLEAUT32!__imp_SysFreeString` at `0x140046154`
- `OLEAUT32!__imp_SysFreeString` at `0x140046168`
- `ole32!CoCreateInstance` at `0x140045f55`
- `ole32!CoCreateInstance` at `0x140045f55`

## string_xrefs

- `0x140045f6d`: `base\winsat\common\winsatutilities.cpp`
- `0x140046050`: `base\winsat\common\winsatutilities.cpp`
- `0x140046122`: `base\winsat\common\winsatutilities.cpp`
- `0x140046143`: `base\winsat\common\winsatutilities.cpp`
- `0x140045f61`: `cannot disable/enable task, failed to create a TaskScheduler object`
- `0x140045ff9`: `cannot disable/enable task, failed to connect to the TaskScheduler `
- `0x140046044`: `cannot disable/enable task, failed to get the root task folder`
- `0x1400460bb`: `cannot disable/enable task, failed to get the WinSAT task`
- `0x1400460e9`: `cannot get the enabled property for the task`
- `0x140046116`: `cannot disable/enable task, failed to get set the enable state`
- `0x140046137`: `%s the WinSAT Task`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EnableDisableWinSATTask(char a1)
{
  HRESULT v1; // ebx
  OLECHAR *v3; // rbx
  int v4; // edi
  OLECHAR *v5; // rdi
  int v6; // esi
  __int16 v7; // [rsp+30h] [rbp-59h] BYREF
  _BYTE v8[22]; // [rsp+32h] [rbp-57h]
  BSTR bstrString; // [rsp+50h] [rbp-39h] BYREF
  BSTR v10; // [rsp+58h] [rbp-31h] BYREF
  __int16 v11; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v12[22]; // [rsp+62h] [rbp-27h]
  __int16 v13; // [rsp+80h] [rbp-9h] BYREF
  _BYTE v14[22]; // [rsp+82h] [rbp-7h]
  __int16 v15; // [rsp+A0h] [rbp+17h] BYREF
  _OWORD v16[3]; // [rsp+A2h] [rbp+19h]
  __int16 v17; // [rsp+F0h] [rbp+67h] BYREF
  LPVOID ppv; // [rsp+F8h] [rbp+6Fh] BYREF
  __int64 v19; // [rsp+100h] [rbp+77h] BYREF
  __int64 v20; // [rsp+108h] [rbp+7Fh] BYREF

  LOBYTE(v17) = a1;
  ppv = 0;
  v1 = CoCreateInstance(&CLSID_TaskScheduler, 0, 0x17u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v1 < 0 )
  {
    Log_Text_F(
      "base\\winsat\\common\\winsatutilities.cpp",
      1389,
      "cannot disable/enable task, failed to create a TaskScheduler object");
LABEL_3:
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>((__int64 *)&ppv);
    return (unsigned int)v1;
  }
  *(_OWORD *)v8 = 0;
  *(_WORD *)&v8[14] = 0;
  v11 = 1;
  *(_OWORD *)v12 = *(_OWORD *)v8;
  *(_QWORD *)&v12[14] = 0;
  v13 = 1;
  *(_OWORD *)v14 = *(_OWORD *)v8;
  *(_QWORD *)&v14[14] = 0;
  v15 = 1;
  v16[0] = *(_OWORD *)v8;
  *(_QWORD *)((char *)v16 + 14) = 0;
  v7 = 1;
  *(_QWORD *)&v8[14] = 0;
  if ( (*(int (__fastcall **)(LPVOID, __int16 *, __int16 *, __int16 *, __int16 *))(*(_QWORD *)ppv + 80LL))(
         ppv,
         &v7,
         &v15,
         &v13,
         &v11) < 0 )
  {
    Log_Text_F(
      "base\\winsat\\common\\winsatutilities.cpp",
      1396,
      "cannot disable/enable task, failed to connect to the TaskScheduler ");
    goto LABEL_3;
  }
  v20 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"\\Microsoft\\Windows\\Maintenance");
  v3 = bstrString;
  v4 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, bstrString, &v20);
  if ( v4 >= 0 )
  {
    v19 = 0;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v10, L"WinSAT");
    v5 = v10;
    v6 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v20 + 104LL))(v20, v10, &v19);
    if ( v6 >= 0 )
    {
      v17 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v19 + 80LL))(v19, &v17);
      if ( v6 >= 0 )
      {
        if ( v17 == -1 || (v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 88LL))(v19), v6 >= 0) )
        {
          Log_Text_F("base\\winsat\\common\\winsatutilities.cpp", 1443, "%s the WinSAT Task", "Enabling");
          v6 = 0;
        }
        else
        {
          Log_Text_F(
            "base\\winsat\\common\\winsatutilities.cpp",
            1439,
            "cannot disable/enable task, failed to get set the enable state");
        }
      }
      else
      {
        Log_Text_F("base\\winsat\\common\\winsatutilities.cpp", 1424, "cannot get the enabled property for the task");
      }
    }
    else
    {
      Log_Text_F(
        "base\\winsat\\common\\winsatutilities.cpp",
        1416,
        "cannot disable/enable task, failed to get the WinSAT task");
    }
    SysFreeString(v5);
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v19);
    SysFreeString(v3);
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>((__int64 *)&ppv);
    return (unsigned int)v6;
  }
  else
  {
    Log_Text_F(
      "base\\winsat\\common\\winsatutilities.cpp",
      1406,
      "cannot disable/enable task, failed to get the root task folder");
    SysFreeString(v3);
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(&v20);
    ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>((__int64 *)&ppv);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x140045f1c  mov     byte ptr [rsp-8+arg_0], cl
0x140045f20  push    rbp
0x140045f21  push    rbx
0x140045f22  push    rsi
0x140045f23  push    rdi
0x140045f24  lea     rbp, [rsp-3Fh]
0x140045f29  sub     rsp, 0C8h
0x140045f30  mov     [rbp+57h+arg_8], 0
0x140045f38  lea     rax, [rbp+57h+arg_8]
0x140045f3c  mov     [rsp+0E0h+ppv], rax; ppv
0x140045f41  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x140045f48  xor     edx, edx; pUnkOuter
0x140045f4a  lea     r8d, [rdx+17h]; dwClsContext
0x140045f4e  lea     rcx, CLSID_TaskScheduler; rclsid
0x140045f55  call    cs:__imp_CoCreateInstance
0x140045f5b  mov     ebx, eax
0x140045f5d  test    eax, eax
0x140045f5f  jns     short loc_140045F8A
0x140045f61  lea     r8, aCannotDisableE_0; "cannot disable/enable task, failed to c"...
0x140045f68  mov     edx, 56Dh
0x140045f6d  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x140045f74  call    Log_Text_F
0x140045f79  nop
0x140045f7a  lea     rcx, [rbp+57h+arg_8]
0x140045f7e  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140045f83  mov     eax, ebx
0x140045f85  jmp     loc_140046184
0x140045f8a  mov     edx, 1
0x140045f8f  xorps   xmm0, xmm0
0x140045f92  xor     eax, eax
0x140045f94  movups  xmmword ptr [rbp+57h+var_AE], xmm0
0x140045f98  mov     qword ptr [rbp+57h+var_AE+0Eh], rax
0x140045f9c  mov     rcx, [rbp+57h+arg_8]
0x140045fa0  mov     [rbp+57h+var_80], dx
0x140045fa4  movups  xmm1, xmmword ptr [rbp+57h+var_AE]
0x140045fa8  movups  xmmword ptr [rbp+57h+var_7E], xmm1
0x140045fac  mov     qword ptr [rbp+57h+var_7E+0Eh], rax
0x140045fb0  mov     [rbp+57h+var_60], dx
0x140045fb4  movups  xmmword ptr [rbp+57h+var_5E], xmm1
0x140045fb8  mov     qword ptr [rbp+57h+var_5E+0Eh], rax
0x140045fbc  mov     [rbp+57h+var_40], dx
0x140045fc0  movups  [rbp+57h+var_3E], xmm1
0x140045fc4  mov     qword ptr [rbp+57h+var_3E+0Eh], rax
0x140045fc8  mov     [rbp+57h+var_B0], dx
0x140045fcc  movups  xmmword ptr [rbp+57h+var_AE], xmm1
0x140045fd0  mov     qword ptr [rbp+57h+var_AE+0Eh], rax
0x140045fd4  mov     rax, [rcx]
0x140045fd7  lea     rdx, [rbp+57h+var_80]
0x140045fdb  mov     [rsp+0E0h+ppv], rdx
0x140045fe0  lea     r9, [rbp+57h+var_60]
0x140045fe4  lea     r8, [rbp+57h+var_40]
0x140045fe8  lea     rdx, [rbp+57h+var_B0]
0x140045fec  mov     rax, [rax+50h]
0x140045ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045ff5  test    eax, eax
0x140045ff7  jns     short loc_14004600A
0x140045ff9  lea     r8, aCannotDisableE_2; "cannot disable/enable task, failed to c"...
0x140046000  mov     edx, 574h
0x140046005  jmp     loc_140045F6D
0x14004600a  mov     [rbp+57h+arg_18], 0
0x140046012  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Maintenance"
0x140046019  lea     rcx, [rbp+57h+bstrString]; this
0x14004601d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140046022  nop
0x140046023  mov     rcx, [rbp+57h+arg_8]
0x140046027  mov     rax, [rcx]
0x14004602a  lea     r8, [rbp+57h+arg_18]
0x14004602e  mov     rbx, [rbp+57h+bstrString]
0x140046032  mov     rdx, rbx
0x140046035  mov     rax, [rax+38h]
0x140046039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004603e  mov     edi, eax
0x140046040  test    eax, eax
0x140046042  jns     short loc_140046081
0x140046044  lea     r8, aCannotDisableE_3; "cannot disable/enable task, failed to g"...
0x14004604b  mov     edx, 57Eh
0x140046050  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x140046057  call    Log_Text_F
0x14004605c  nop
0x14004605d  mov     rcx, rbx; bstrString
0x140046060  call    cs:__imp_SysFreeString
0x140046066  nop
0x140046067  lea     rcx, [rbp+57h+arg_18]
0x14004606b  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140046070  nop
0x140046071  lea     rcx, [rbp+57h+arg_8]
0x140046075  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x14004607a  mov     eax, edi
0x14004607c  jmp     loc_140046184
0x140046081  mov     [rbp+57h+arg_10], 0
0x140046089  lea     rdx, aWinsat_3; "WinSAT"
0x140046090  lea     rcx, [rbp+57h+var_88]; this
0x140046094  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x140046099  nop
0x14004609a  mov     rcx, [rbp+57h+arg_18]
0x14004609e  mov     rax, [rcx]
0x1400460a1  lea     r8, [rbp+57h+arg_10]
0x1400460a5  mov     rdi, [rbp+57h+var_88]
0x1400460a9  mov     rdx, rdi
0x1400460ac  mov     rax, [rax+68h]
0x1400460b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400460b5  mov     esi, eax
0x1400460b7  test    eax, eax
0x1400460b9  jns     short loc_1400460C9
0x1400460bb  lea     r8, aCannotDisableE_1; "cannot disable/enable task, failed to g"...
0x1400460c2  mov     edx, 588h
0x1400460c7  jmp     short loc_140046122
0x1400460c9  xor     eax, eax
0x1400460cb  mov     [rbp+57h+arg_0], ax
0x1400460cf  mov     rcx, [rbp+57h+arg_10]
0x1400460d3  mov     rax, [rcx]
0x1400460d6  lea     rdx, [rbp+57h+arg_0]
0x1400460da  mov     rax, [rax+50h]
0x1400460de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400460e3  mov     esi, eax
0x1400460e5  test    eax, eax
0x1400460e7  jns     short loc_1400460F7
0x1400460e9  lea     r8, aCannotGetTheEn; "cannot get the enabled property for the"...
0x1400460f0  mov     edx, 590h
0x1400460f5  jmp     short loc_140046122
0x1400460f7  or      edx, 0FFFFFFFFh
0x1400460fa  cmp     [rbp+57h+arg_0], dx
0x1400460fe  jz      short loc_140046130
0x140046100  mov     rcx, [rbp+57h+arg_10]
0x140046104  mov     rax, [rcx]
0x140046107  mov     rax, [rax+58h]
0x14004610b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046110  mov     esi, eax
0x140046112  test    eax, eax
0x140046114  jns     short loc_140046130
0x140046116  lea     r8, aCannotDisableE; "cannot disable/enable task, failed to g"...
0x14004611d  mov     edx, 59Fh
0x140046122  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x140046129  call    Log_Text_F
0x14004612e  jmp     short loc_140046151
0x140046130  lea     r9, aEnabling; "Enabling"
0x140046137  lea     r8, aSTheWinsatTask; "%s the WinSAT Task"
0x14004613e  mov     edx, 5A3h
0x140046143  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x14004614a  call    Log_Text_F
0x14004614f  xor     esi, esi
0x140046151  mov     rcx, rdi; bstrString
0x140046154  call    cs:__imp_SysFreeString
0x14004615a  nop
0x14004615b  lea     rcx, [rbp+57h+arg_10]
0x14004615f  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140046164  nop
0x140046165  mov     rcx, rbx; bstrString
0x140046168  call    cs:__imp_SysFreeString
0x14004616e  nop
0x14004616f  lea     rcx, [rbp+57h+arg_18]
0x140046173  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140046178  nop
0x140046179  lea     rcx, [rbp+57h+arg_8]
0x14004617d  call    ??1?$CComPtrBase@UIRegisteredTask@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IRegisteredTask>::~CComPtrBase<IRegisteredTask>(void)
0x140046182  mov     eax, esi
0x140046184  add     rsp, 0C8h
0x14004618b  pop     rdi
0x14004618c  pop     rsi
0x14004618d  pop     rbx
0x14004618e  pop     rbp
0x14004618f  retn
```
