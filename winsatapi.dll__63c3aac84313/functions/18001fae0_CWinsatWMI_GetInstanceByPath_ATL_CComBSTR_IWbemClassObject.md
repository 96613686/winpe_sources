# CWinsatWMI::GetInstanceByPath(ATL::CComBSTR,IWbemClassObject * *)

- ea: `0x18001fae0`
- end: `0x18001fd46`
- name: `?GetInstanceByPath@CWinsatWMI@@EEAAJVCComBSTR@ATL@@PEAPEAUIWbemClassObject@@@Z`
- size: `614`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001a34`
- `0x180013f80`
- `0x18001d79c`
- `0x18001fae0`
- `0x180031010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001fc8e`
- `msvcrt!_wcsicmp` at `0x18001fc8e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fb37`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fc74`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fc9b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd06`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fb37`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fc74`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fc9b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd06`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fb5b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fba0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fd2a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fb5b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fba0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001fd2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWinsatWMI::GetInstanceByPath(_QWORD **a1, BSTR *a2, _QWORD *a3)
{
  __int64 (__fastcall *v7)(_QWORD **, __int64, _QWORD, __int64); // rbx
  ATL::CComBSTR *v8; // rax
  int v9; // edi
  unsigned __int64 v10; // rax
  wchar_t *v11; // rax
  wchar_t *v12; // rbx
  wchar_t *v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // [rsp+30h] [rbp-20h] BYREF
  __int64 v16; // [rsp+38h] [rbp-18h] BYREF
  BSTR bstrString[2]; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+30h] BYREF
  int v19; // [rsp+88h] [rbp+38h] BYREF
  __int64 v20; // [rsp+98h] [rbp+48h] BYREF

  bstrString[1] = (BSTR)-2LL;
  v16 = 0;
  v20 = 0;
  v15 = 0;
  if ( ((int (__fastcall *)(_QWORD **, BSTR, __int64 *))(*a1)[6])(a1, *a2, &v16) < 0 )
  {
    operator delete(0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
    SysFreeString(*a2);
    return 2147749896LL;
  }
  v7 = (__int64 (__fastcall *)(_QWORD **, __int64, _QWORD, __int64))(*a1)[7];
  v8 = ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)bstrString, L"Win32_WinSAT");
  LODWORD(v7) = v7(a1, v16, *(_QWORD *)v8, 8);
  SysFreeString(bstrString[0]);
  if ( (int)v7 < 0 )
    goto LABEL_7;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v16 + 176LL))(v16, &v20);
  if ( v9 < 0 )
    goto LABEL_13;
  v19 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 24LL))(v20, &v19);
  if ( v9 < 0 )
    goto LABEL_13;
  if ( v19 != 1
    || (v18 = 0, (*(int (__fastcall **)(__int64, __int64, unsigned int *))(*(_QWORD *)v20 + 96LL))(v20, 2, &v18) < 0) )
  {
LABEL_7:
    v9 = -2147217400;
LABEL_13:
    v13 = 0;
LABEL_26:
    operator delete(v13);
    goto LABEL_27;
  }
  v10 = 2LL * v18;
  if ( !is_mul_ok(v18, 2u) )
    v10 = -1;
  v11 = (wchar_t *)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v11;
  if ( !v11 )
  {
    v9 = -2147217402;
    goto LABEL_13;
  }
  if ( (*(int (__fastcall **)(__int64, __int64, unsigned int *, wchar_t *))(*(_QWORD *)v20 + 96LL))(v20, 2, &v18, v11) >= 0 )
  {
    if ( !_wcsicmp(L"TimeTaken=\"MostRecentAssessment\"", v12) )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, __int64 *))(*a1[11] + 120LL))(a1[11], 0, &v15);
      if ( v9 >= 0 )
      {
        v9 = ((__int64 (__fastcall *)(_QWORD **, __int64))(*a1)[4])(a1, v15);
        if ( v9 >= 0 )
        {
          if ( a3 )
          {
            v14 = v15;
            *a3 = v15;
            if ( v14 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
            v9 = 0;
          }
          else
          {
            v9 = -2147467261;
          }
        }
      }
      v13 = v12;
      goto LABEL_26;
    }
    operator delete(v12);
    v9 = -2147217406;
  }
  else
  {
    operator delete(v12);
    v9 = -2147217400;
  }
LABEL_27:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v15);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v16);
  SysFreeString(*a2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001fae0  mov     rax, rsp
0x18001fae3  push    rbp
0x18001fae4  push    rsi
0x18001fae5  push    rdi
0x18001fae6  push    r14
0x18001fae8  push    r15
0x18001faea  mov     rbp, rsp
0x18001faed  sub     rsp, 50h
0x18001faf1  mov     [rbp+var_8], 0FFFFFFFFFFFFFFFEh
0x18001faf9  mov     [rax+18h], rbx
0x18001fafd  mov     r14, r8
0x18001fb00  mov     r15, rdx
0x18001fb03  mov     rsi, rcx
0x18001fb06  mov     [rbp+var_18], 0
0x18001fb0e  mov     [rbp+arg_18], 0
0x18001fb16  mov     [rbp+var_20], 0
0x18001fb1e  mov     rax, [rcx]
0x18001fb21  lea     r8, [rbp+var_18]
0x18001fb25  mov     rdx, [rdx]
0x18001fb28  mov     rax, [rax+30h]
0x18001fb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb31  test    eax, eax
0x18001fb33  jns     short loc_18001FB6B
0x18001fb35  xor     ecx, ecx
0x18001fb37  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fb3d  lea     rcx, [rbp+var_20]
0x18001fb41  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fb46  lea     rcx, [rbp+arg_18]
0x18001fb4a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fb4f  lea     rcx, [rbp+var_18]
0x18001fb53  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fb58  mov     rcx, [r15]; bstrString
0x18001fb5b  call    cs:__imp_SysFreeString
0x18001fb61  mov     eax, 80041008h
0x18001fb66  jmp     loc_18001FD32
0x18001fb6b  mov     rax, [rsi]
0x18001fb6e  mov     rbx, [rax+38h]
0x18001fb72  lea     rdx, aWin32Winsat; "Win32_WinSAT"
0x18001fb79  lea     rcx, [rbp+bstrString]; this
0x18001fb7d  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18001fb82  mov     r9d, 8
0x18001fb88  mov     r8, [rax]
0x18001fb8b  mov     rdx, [rbp+var_18]
0x18001fb8f  mov     rcx, rsi
0x18001fb92  mov     rax, rbx
0x18001fb95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb9a  mov     ebx, eax
0x18001fb9c  mov     rcx, [rbp+bstrString]; bstrString
0x18001fba0  call    cs:__imp_SysFreeString
0x18001fba6  test    ebx, ebx
0x18001fba8  js      short loc_18001FBF2
0x18001fbaa  mov     rcx, [rbp+var_18]
0x18001fbae  mov     rax, [rcx]
0x18001fbb1  lea     rdx, [rbp+arg_18]
0x18001fbb5  mov     rax, [rax+0B0h]
0x18001fbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbc1  mov     edi, eax
0x18001fbc3  test    eax, eax
0x18001fbc5  js      loc_18001FC4D
0x18001fbcb  mov     [rbp+arg_8], 0
0x18001fbd2  mov     rcx, [rbp+arg_18]
0x18001fbd6  mov     rax, [rcx]
0x18001fbd9  lea     rdx, [rbp+arg_8]
0x18001fbdd  mov     rax, [rax+18h]
0x18001fbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fbe6  mov     edi, eax
0x18001fbe8  test    eax, eax
0x18001fbea  js      short loc_18001FC4D
0x18001fbec  cmp     [rbp+arg_8], 1
0x18001fbf0  jz      short loc_18001FBF9
0x18001fbf2  mov     edi, 80041008h
0x18001fbf7  jmp     short loc_18001FC4D
0x18001fbf9  mov     [rbp+arg_0], 0
0x18001fc00  mov     rcx, [rbp+arg_18]
0x18001fc04  mov     rax, [rcx]
0x18001fc07  xor     r9d, r9d
0x18001fc0a  lea     r8, [rbp+arg_0]
0x18001fc0e  lea     edi, [r9+2]
0x18001fc12  mov     edx, edi
0x18001fc14  mov     rax, [rax+60h]
0x18001fc18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc1d  test    eax, eax
0x18001fc1f  js      short loc_18001FBF2
0x18001fc21  mov     ecx, [rbp+arg_0]
0x18001fc24  mov     eax, edi
0x18001fc26  mul     rcx
0x18001fc29  lea     rcx, [rdi-3]
0x18001fc2d  cmovb   rax, rcx
0x18001fc31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fc38  mov     rcx, rax; unsigned __int64
0x18001fc3b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001fc40  mov     rbx, rax
0x18001fc43  test    rax, rax
0x18001fc46  jnz     short loc_18001FC54
0x18001fc48  mov     edi, 80041006h
0x18001fc4d  xor     ecx, ecx
0x18001fc4f  jmp     loc_18001FD06
0x18001fc54  mov     rcx, [rbp+arg_18]
0x18001fc58  mov     rax, [rcx]
0x18001fc5b  mov     r9, rbx
0x18001fc5e  lea     r8, [rbp+arg_0]
0x18001fc62  mov     edx, edi
0x18001fc64  mov     rax, [rax+60h]
0x18001fc68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc6d  test    eax, eax
0x18001fc6f  jns     short loc_18001FC84
0x18001fc71  mov     rcx, rbx
0x18001fc74  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fc7a  mov     edi, 80041008h
0x18001fc7f  jmp     loc_18001FD0C
0x18001fc84  mov     rdx, rbx; String2
0x18001fc87  lea     rcx, aTimetakenMostr; "TimeTaken=\"MostRecentAssessment\""
0x18001fc8e  call    cs:__imp__wcsicmp
0x18001fc94  test    eax, eax
0x18001fc96  jz      short loc_18001FCA8
0x18001fc98  mov     rcx, rbx
0x18001fc9b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fca1  mov     edi, 80041002h
0x18001fca6  jmp     short loc_18001FD0C
0x18001fca8  mov     rcx, [rsi+58h]
0x18001fcac  mov     rax, [rcx]
0x18001fcaf  lea     r8, [rbp+var_20]
0x18001fcb3  xor     edx, edx
0x18001fcb5  mov     rax, [rax+78h]
0x18001fcb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcbe  mov     edi, eax
0x18001fcc0  test    eax, eax
0x18001fcc2  js      short loc_18001FD03
0x18001fcc4  mov     rax, [rsi]
0x18001fcc7  mov     rdx, [rbp+var_20]
0x18001fccb  mov     rcx, rsi
0x18001fcce  mov     rax, [rax+20h]
0x18001fcd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fcd7  mov     edi, eax
0x18001fcd9  test    eax, eax
0x18001fcdb  js      short loc_18001FD03
0x18001fcdd  test    r14, r14
0x18001fce0  jnz     short loc_18001FCE9
0x18001fce2  mov     edi, 80004003h
0x18001fce7  jmp     short loc_18001FD03
0x18001fce9  mov     rcx, [rbp+var_20]
0x18001fced  mov     [r14], rcx
0x18001fcf0  test    rcx, rcx
0x18001fcf3  jz      short loc_18001FD01
0x18001fcf5  mov     rax, [rcx]
0x18001fcf8  mov     rax, [rax+8]
0x18001fcfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd01  xor     edi, edi
0x18001fd03  mov     rcx, rbx
0x18001fd06  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fd0c  lea     rcx, [rbp+var_20]
0x18001fd10  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fd15  lea     rcx, [rbp+arg_18]
0x18001fd19  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fd1e  lea     rcx, [rbp+var_18]
0x18001fd22  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001fd27  mov     rcx, [r15]; bstrString
0x18001fd2a  call    cs:__imp_SysFreeString
0x18001fd30  mov     eax, edi
0x18001fd32  mov     rbx, [rsp+50h+arg_10]
0x18001fd3a  add     rsp, 50h
0x18001fd3e  pop     r15
0x18001fd40  pop     r14
0x18001fd42  pop     rdi
0x18001fd43  pop     rsi
0x18001fd44  pop     rbp
0x18001fd45  retn
```
