# EnableDisableWinSATTask(bool)

- ea: `0x180023a94`
- end: `0x180023d0b`
- name: `?EnableDisableWinSATTask@@YAJ_N@Z`
- size: `631`
- prototype: `__int64 __fastcall(char)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180020dcc`
- `0x1800211f8`

## callees

- `0x180001a34`
- `0x18000e6ac`
- `0x18001d79c`
- `0x180023a94`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180023bdd`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ccd`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ce1`
- `OLEAUT32!__imp_SysFreeString` at `0x180023bdd`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ccd`
- `OLEAUT32!__imp_SysFreeString` at `0x180023ce1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023ad6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180023ad6`

## string_xrefs

- `0x180023aee`: `base\winsat\common\winsatutilities.cpp`
- `0x180023bcd`: `base\winsat\common\winsatutilities.cpp`
- `0x180023c9a`: `base\winsat\common\winsatutilities.cpp`
- `0x180023cbb`: `base\winsat\common\winsatutilities.cpp`
- `0x180023ae2`: `cannot disable/enable task, failed to create a TaskScheduler object`
- `0x180023b7a`: `cannot disable/enable task, failed to connect to the TaskScheduler `
- `0x180023bc1`: `cannot disable/enable task, failed to get the root task folder`
- `0x180023c34`: `cannot disable/enable task, failed to get the WinSAT task`
- `0x180023c61`: `cannot get the enabled property for the task`
- `0x180023c8e`: `cannot disable/enable task, failed to get set the enable state`
- `0x180023caf`: `%s the WinSAT Task`

## pseudocode

```c
__int64 __fastcall EnableDisableWinSATTask(char a1)
{
  HRESULT v1; // ebx
  OLECHAR *v3; // rbx
  int v4; // edi
  OLECHAR *v5; // rdi
  int v6; // esi
  __int16 v7; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v8[22]; // [rsp+32h] [rbp-67h]
  BSTR bstrString; // [rsp+50h] [rbp-49h] BYREF
  BSTR v10; // [rsp+58h] [rbp-41h] BYREF
  __int16 v11; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v12[22]; // [rsp+62h] [rbp-37h]
  __int16 v13; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v14[22]; // [rsp+82h] [rbp-17h]
  __int16 v15; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v16[22]; // [rsp+A2h] [rbp+9h]
  __int64 v17; // [rsp+C0h] [rbp+27h]
  __int16 v18; // [rsp+100h] [rbp+67h] BYREF
  LPVOID ppv; // [rsp+108h] [rbp+6Fh] BYREF
  __int64 v20; // [rsp+110h] [rbp+77h] BYREF
  __int64 v21; // [rsp+118h] [rbp+7Fh] BYREF

  LOBYTE(v18) = a1;
  v17 = -2;
  ppv = 0;
  v1 = CoCreateInstance(&CLSID_TaskScheduler, 0, 0x17u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
  if ( v1 < 0 )
  {
    Log_Text_F(
      "base\\winsat\\common\\winsatutilities.cpp",
      1389,
      "cannot disable/enable task, failed to create a TaskScheduler object");
LABEL_3:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
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
  *(_OWORD *)v16 = *(_OWORD *)v8;
  *(_QWORD *)&v16[14] = 0;
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
  v21 = 0;
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"\\Microsoft\\Windows\\Maintenance");
  v3 = bstrString;
  v4 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, bstrString, &v21);
  if ( v4 >= 0 )
  {
    v20 = 0;
    ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&v10, L"WinSAT");
    v5 = v10;
    v6 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v21 + 104LL))(v21, v10, &v20);
    if ( v6 >= 0 )
    {
      v18 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, __int16 *))(*(_QWORD *)v20 + 80LL))(v20, &v18);
      if ( v6 >= 0 )
      {
        if ( v18 && (v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 88LL))(v20, 0), v6 < 0) )
        {
          Log_Text_F(
            "base\\winsat\\common\\winsatutilities.cpp",
            1439,
            "cannot disable/enable task, failed to get set the enable state");
        }
        else
        {
          Log_Text_F("base\\winsat\\common\\winsatutilities.cpp", 1443, "%s the WinSAT Task", "Diabling");
          v6 = 0;
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
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    SysFreeString(v3);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    return (unsigned int)v6;
  }
  else
  {
    Log_Text_F(
      "base\\winsat\\common\\winsatutilities.cpp",
      1406,
      "cannot disable/enable task, failed to get the root task folder");
    SysFreeString(v3);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    return (unsigned int)v4;
  }
}

```

## disassembly

```asm
0x180023a94  mov     byte ptr [rsp-8+arg_0], cl
0x180023a98  push    rbp
0x180023a99  push    rbx
0x180023a9a  push    rsi
0x180023a9b  push    rdi
0x180023a9c  push    r14
0x180023a9e  lea     rbp, [rsp-37h]
0x180023aa3  sub     rsp, 0D0h
0x180023aaa  mov     [rbp+57h+var_30], 0FFFFFFFFFFFFFFFEh
0x180023ab2  xor     r14d, r14d
0x180023ab5  mov     [rbp+57h+arg_8], r14
0x180023ab9  lea     rax, [rbp+57h+arg_8]
0x180023abd  mov     [rsp+0F0h+ppv], rax; ppv
0x180023ac2  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180023ac9  xor     edx, edx; pUnkOuter
0x180023acb  lea     r8d, [r14+17h]; dwClsContext
0x180023acf  lea     rcx, CLSID_TaskScheduler; rclsid
0x180023ad6  call    cs:__imp_CoCreateInstance
0x180023adc  mov     ebx, eax
0x180023ade  test    eax, eax
0x180023ae0  jns     short loc_180023B0B
0x180023ae2  lea     r8, aCannotDisableE_0; "cannot disable/enable task, failed to c"...
0x180023ae9  mov     edx, 56Dh
0x180023aee  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x180023af5  call    Log_Text_F
0x180023afa  nop
0x180023afb  lea     rcx, [rbp+57h+arg_8]
0x180023aff  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023b04  mov     eax, ebx
0x180023b06  jmp     loc_180023CFD
0x180023b0b  mov     edx, 1
0x180023b10  xorps   xmm0, xmm0
0x180023b13  xor     eax, eax
0x180023b15  movups  xmmword ptr [rbp+57h+var_BE], xmm0
0x180023b19  mov     qword ptr [rbp+57h+var_BE+0Eh], rax
0x180023b1d  mov     rcx, [rbp+57h+arg_8]
0x180023b21  mov     [rbp+57h+var_90], dx
0x180023b25  movups  xmm1, xmmword ptr [rbp+57h+var_BE]
0x180023b29  movups  xmmword ptr [rbp+57h+var_8E], xmm1
0x180023b2d  mov     qword ptr [rbp+57h+var_8E+0Eh], rax
0x180023b31  mov     [rbp+57h+var_70], dx
0x180023b35  movups  xmmword ptr [rbp+57h+var_6E], xmm1
0x180023b39  mov     qword ptr [rbp+57h+var_6E+0Eh], rax
0x180023b3d  mov     [rbp+57h+var_50], dx
0x180023b41  movups  xmmword ptr [rbp+57h+var_4E], xmm1
0x180023b45  mov     qword ptr [rbp+57h+var_4E+0Eh], rax
0x180023b49  mov     [rbp+57h+var_C0], dx
0x180023b4d  movups  xmmword ptr [rbp+57h+var_BE], xmm1
0x180023b51  mov     qword ptr [rbp+57h+var_BE+0Eh], rax
0x180023b55  mov     rax, [rcx]
0x180023b58  lea     rdx, [rbp+57h+var_90]
0x180023b5c  mov     [rsp+0F0h+ppv], rdx
0x180023b61  lea     r9, [rbp+57h+var_70]
0x180023b65  lea     r8, [rbp+57h+var_50]
0x180023b69  lea     rdx, [rbp+57h+var_C0]
0x180023b6d  mov     rax, [rax+50h]
0x180023b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b76  test    eax, eax
0x180023b78  jns     short loc_180023B8B
0x180023b7a  lea     r8, aCannotDisableE_2; "cannot disable/enable task, failed to c"...
0x180023b81  mov     edx, 574h
0x180023b86  jmp     loc_180023AEE
0x180023b8b  mov     [rbp+57h+arg_18], r14
0x180023b8f  lea     rdx, aMicrosoftWindo; "\\Microsoft\\Windows\\Maintenance"
0x180023b96  lea     rcx, [rbp+57h+bstrString]; this
0x180023b9a  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180023b9f  nop
0x180023ba0  mov     rcx, [rbp+57h+arg_8]
0x180023ba4  mov     rax, [rcx]
0x180023ba7  lea     r8, [rbp+57h+arg_18]
0x180023bab  mov     rbx, [rbp+57h+bstrString]
0x180023baf  mov     rdx, rbx
0x180023bb2  mov     rax, [rax+38h]
0x180023bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bbb  mov     edi, eax
0x180023bbd  test    eax, eax
0x180023bbf  jns     short loc_180023BFE
0x180023bc1  lea     r8, aCannotDisableE_3; "cannot disable/enable task, failed to g"...
0x180023bc8  mov     edx, 57Eh
0x180023bcd  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x180023bd4  call    Log_Text_F
0x180023bd9  nop
0x180023bda  mov     rcx, rbx; bstrString
0x180023bdd  call    cs:__imp_SysFreeString
0x180023be3  nop
0x180023be4  lea     rcx, [rbp+57h+arg_18]
0x180023be8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023bed  nop
0x180023bee  lea     rcx, [rbp+57h+arg_8]
0x180023bf2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023bf7  mov     eax, edi
0x180023bf9  jmp     loc_180023CFD
0x180023bfe  mov     [rbp+57h+arg_10], r14
0x180023c02  lea     rdx, aWinsat_0; "WinSAT"
0x180023c09  lea     rcx, [rbp+57h+var_98]; this
0x180023c0d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180023c12  nop
0x180023c13  mov     rcx, [rbp+57h+arg_18]
0x180023c17  mov     rax, [rcx]
0x180023c1a  lea     r8, [rbp+57h+arg_10]
0x180023c1e  mov     rdi, [rbp+57h+var_98]
0x180023c22  mov     rdx, rdi
0x180023c25  mov     rax, [rax+68h]
0x180023c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c2e  mov     esi, eax
0x180023c30  test    eax, eax
0x180023c32  jns     short loc_180023C42
0x180023c34  lea     r8, aCannotDisableE_1; "cannot disable/enable task, failed to g"...
0x180023c3b  mov     edx, 588h
0x180023c40  jmp     short loc_180023C9A
0x180023c42  mov     [rbp+57h+arg_0], r14w
0x180023c47  mov     rcx, [rbp+57h+arg_10]
0x180023c4b  mov     rax, [rcx]
0x180023c4e  lea     rdx, [rbp+57h+arg_0]
0x180023c52  mov     rax, [rax+50h]
0x180023c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c5b  mov     esi, eax
0x180023c5d  test    eax, eax
0x180023c5f  jns     short loc_180023C6F
0x180023c61  lea     r8, aCannotGetTheEn; "cannot get the enabled property for the"...
0x180023c68  mov     edx, 590h
0x180023c6d  jmp     short loc_180023C9A
0x180023c6f  cmp     [rbp+57h+arg_0], r14w
0x180023c74  jz      short loc_180023CA8
0x180023c76  mov     rcx, [rbp+57h+arg_10]
0x180023c7a  mov     rax, [rcx]
0x180023c7d  xor     edx, edx
0x180023c7f  mov     rax, [rax+58h]
0x180023c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c88  mov     esi, eax
0x180023c8a  test    eax, eax
0x180023c8c  jns     short loc_180023CA8
0x180023c8e  lea     r8, aCannotDisableE; "cannot disable/enable task, failed to g"...
0x180023c95  mov     edx, 59Fh
0x180023c9a  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x180023ca1  call    Log_Text_F
0x180023ca6  jmp     short loc_180023CCA
0x180023ca8  lea     r9, aDiabling; "Diabling"
0x180023caf  lea     r8, aSTheWinsatTask; "%s the WinSAT Task"
0x180023cb6  mov     edx, 5A3h
0x180023cbb  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x180023cc2  call    Log_Text_F
0x180023cc7  mov     esi, r14d
0x180023cca  mov     rcx, rdi; bstrString
0x180023ccd  call    cs:__imp_SysFreeString
0x180023cd3  nop
0x180023cd4  lea     rcx, [rbp+57h+arg_10]
0x180023cd8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023cdd  nop
0x180023cde  mov     rcx, rbx; bstrString
0x180023ce1  call    cs:__imp_SysFreeString
0x180023ce7  nop
0x180023ce8  lea     rcx, [rbp+57h+arg_18]
0x180023cec  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023cf1  nop
0x180023cf2  lea     rcx, [rbp+57h+arg_8]
0x180023cf6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180023cfb  mov     eax, esi
0x180023cfd  add     rsp, 0D0h
0x180023d04  pop     r14
0x180023d06  pop     rdi
0x180023d07  pop     rsi
0x180023d08  pop     rbx
0x180023d09  pop     rbp
0x180023d0a  retn
```
