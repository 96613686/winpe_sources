# CShellQuery::_WaitForItems(IRowset *)

- ea: `0x140089364`
- end: `0x140089535`
- name: `?_WaitForItems@CShellQuery@@IEAAJPEAUIRowset@@@Z`
- size: `465`
- prototype: `__int64 __fastcall(IUnknown *this, IUnknown *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140029c80`

## callees

- `0x140024688`
- `0x140047798`
- `0x140083678`
- `0x140088f50`
- `0x140089364`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x14008940e`
- `KERNEL32!CreateEventW` at `0x14008940e`
- `KERNEL32!GetLastError` at `0x14008941d`
- `KERNEL32!GetLastError` at `0x14008941d`
- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x140089466`
- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x14008950b`
- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x140089466`
- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x14008950b`

## pseudocode

```c
__int64 __fastcall CShellQuery::_WaitForItems(IUnknown *this, IUnknown *a2)
{
  int v3; // ebx
  IUnknown *v4; // rdi
  struct IUnknownVtbl *EventW; // rax
  signed int LastError; // eax
  __int64 v8[3]; // [rsp+30h] [rbp-18h] BYREF
  IUnknown *punk; // [rsp+70h] [rbp+28h] BYREF
  unsigned int v10; // [rsp+78h] [rbp+30h] BYREF
  DWORD pdwCookie; // [rsp+80h] [rbp+38h] BYREF
  int v12; // [rsp+88h] [rbp+40h] BYREF

  punk = this;
  v8[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_10cc32c7a2eb32aaa8826d527a7df3a8_Traceguids);
  }
  v3 = ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_42811652_079d_481b_87a2_09a69ecc5f44,
         v8);
  if ( v3 >= 0 )
  {
    punk = 0;
    v3 = ATL::CComObject<CShellResultsListenerWait>::CreateInstance(&punk);
    if ( v3 >= 0 )
    {
      v4 = punk;
      ((void (__fastcall *)(IUnknown *))punk->lpVtbl->AddRef)(punk);
      EventW = (struct IUnknownVtbl *)CreateEventW(0, 0, 0, 0);
      v4[11].lpVtbl = EventW;
      if ( EventW )
        goto LABEL_11;
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 >= 0 )
      {
LABEL_11:
        pdwCookie = 0;
        v3 = ConnectToConnectionPoint(v4, &GUID_1551aea5_5d66_4b11_86f5_d5634cb211b9, 1, a2, &pdwCookie, 0);
        if ( v3 >= 0 )
        {
          v12 = 0;
          v10 = 0;
          LODWORD(punk) = 0;
          v3 = (*(__int64 (__fastcall **)(__int64, int *, unsigned int *, IUnknown **))(*(_QWORD *)v8[0] + 40LL))(
                 v8[0],
                 &v12,
                 &v10,
                 &punk);
          if ( v3 >= 0 && (v10 || (_DWORD)punk) )
          {
            v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v8[0] + 24LL))(v8[0], 1, 1000);
            if ( v3 >= 0 )
              CShellResultsListenerWait::WaitForItems((CShellResultsListenerWait *)v4, v10, (unsigned int)punk);
          }
          ConnectToConnectionPoint(v4, &GUID_1551aea5_5d66_4b11_86f5_d5634cb211b9, 0, a2, &pdwCookie, 0);
        }
      }
      ((void (__fastcall *)(IUnknown *))v4->lpVtbl->Release)(v4);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v8);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140089364  mov     [rsp-20h+punk], rcx
0x140089369  push    rbp
0x14008936a  push    rbx
0x14008936b  push    rsi
0x14008936c  push    rdi
0x14008936d  mov     rbp, rsp
0x140089370  sub     rsp, 48h
0x140089374  mov     rsi, rdx
0x140089377  mov     [rbp+var_18], 0
0x14008937f  lea     rax, WPP_GLOBAL_Control
0x140089386  mov     rcx, cs:WPP_GLOBAL_Control
0x14008938d  cmp     rcx, rax
0x140089390  jz      short loc_1400893B3
0x140089392  test    byte ptr [rcx+1Ch], 2
0x140089396  jz      short loc_1400893B3
0x140089398  cmp     byte ptr [rcx+19h], 5
0x14008939c  jb      short loc_1400893B3
0x14008939e  mov     edx, 0Dh
0x1400893a3  lea     r8, WPP_10cc32c7a2eb32aaa8826d527a7df3a8_Traceguids
0x1400893aa  mov     rcx, [rcx+10h]
0x1400893ae  call    WPP_SF_
0x1400893b3  mov     rax, [rsi]
0x1400893b6  lea     r8, [rbp+var_18]
0x1400893ba  lea     rdx, _GUID_42811652_079d_481b_87a2_09a69ecc5f44
0x1400893c1  mov     rcx, rsi
0x1400893c4  mov     rax, [rax]
0x1400893c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400893cc  mov     ebx, eax
0x1400893ce  test    eax, eax
0x1400893d0  js      loc_140089521
0x1400893d6  mov     [rbp+punk], 0
0x1400893de  lea     rcx, [rbp+punk]
0x1400893e2  call    ?CreateInstance@?$CComObject@VCShellResultsListenerWait@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CShellResultsListenerWait>::CreateInstance(ATL::CComObject<CShellResultsListenerWait> * *)
0x1400893e7  mov     ebx, eax
0x1400893e9  test    eax, eax
0x1400893eb  js      loc_140089521
0x1400893f1  mov     rdi, [rbp+punk]
0x1400893f5  mov     rax, [rdi]
0x1400893f8  mov     rcx, rdi
0x1400893fb  mov     rax, [rax+8]
0x1400893ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089404  xor     r9d, r9d; lpName
0x140089407  xor     r8d, r8d; bInitialState
0x14008940a  xor     edx, edx; bManualReset
0x14008940c  xor     ecx, ecx; lpEventAttributes
0x14008940e  call    cs:__imp_CreateEventW
0x140089414  mov     [rdi+58h], rax
0x140089418  test    rax, rax
0x14008941b  jnz     short loc_14008943A
0x14008941d  call    cs:__imp_GetLastError
0x140089423  mov     ebx, eax
0x140089425  test    eax, eax
0x140089427  jle     short loc_140089432
0x140089429  movzx   ebx, ax
0x14008942c  or      ebx, 80070000h
0x140089432  test    ebx, ebx
0x140089434  js      loc_140089511
0x14008943a  mov     [rbp+arg_10], 0
0x140089441  mov     [rsp+48h+ppcpOut], 0; ppcpOut
0x14008944a  lea     rax, [rbp+arg_10]
0x14008944e  mov     [rsp+48h+pdwCookie], rax; pdwCookie
0x140089453  mov     r9, rsi; punkTarget
0x140089456  mov     r8d, 1; fConnect
0x14008945c  lea     rdx, _GUID_1551aea5_5d66_4b11_86f5_d5634cb211b9; riidEvent
0x140089463  mov     rcx, rdi; punk
0x140089466  call    cs:__imp_ConnectToConnectionPoint
0x14008946c  mov     ebx, eax
0x14008946e  test    eax, eax
0x140089470  js      loc_140089511
0x140089476  mov     [rbp+arg_18], 0
0x14008947d  mov     [rbp+arg_8], 0
0x140089484  mov     dword ptr [rbp+punk], 0
0x14008948b  mov     rcx, [rbp+var_18]
0x14008948f  mov     rax, [rcx]
0x140089492  lea     r9, [rbp+punk]
0x140089496  lea     r8, [rbp+arg_8]
0x14008949a  lea     rdx, [rbp+arg_18]
0x14008949e  mov     rax, [rax+28h]
0x1400894a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400894a7  mov     ebx, eax
0x1400894a9  test    eax, eax
0x1400894ab  js      short loc_1400894E9
0x1400894ad  cmp     [rbp+arg_8], 0
0x1400894b1  jnz     short loc_1400894B9
0x1400894b3  cmp     dword ptr [rbp+punk], 0
0x1400894b7  jz      short loc_1400894E9
0x1400894b9  mov     rcx, [rbp+var_18]
0x1400894bd  mov     rax, [rcx]
0x1400894c0  mov     edx, 1
0x1400894c5  mov     r8d, 3E8h
0x1400894cb  mov     rax, [rax+18h]
0x1400894cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400894d4  mov     ebx, eax
0x1400894d6  test    eax, eax
0x1400894d8  js      short loc_1400894E9
0x1400894da  mov     r8d, dword ptr [rbp+punk]; unsigned int
0x1400894de  mov     edx, [rbp+arg_8]; unsigned int
0x1400894e1  mov     rcx, rdi; this
0x1400894e4  call    ?WaitForItems@CShellResultsListenerWait@@QEAAXKK@Z; CShellResultsListenerWait::WaitForItems(ulong,ulong)
0x1400894e9  mov     [rsp+48h+ppcpOut], 0; ppcpOut
0x1400894f2  lea     rax, [rbp+arg_10]
0x1400894f6  mov     [rsp+48h+pdwCookie], rax; pdwCookie
0x1400894fb  mov     r9, rsi; punkTarget
0x1400894fe  xor     r8d, r8d; fConnect
0x140089501  lea     rdx, _GUID_1551aea5_5d66_4b11_86f5_d5634cb211b9; riidEvent
0x140089508  mov     rcx, rdi; punk
0x14008950b  call    cs:__imp_ConnectToConnectionPoint
0x140089511  mov     rax, [rdi]
0x140089514  mov     rcx, rdi
0x140089517  mov     rax, [rax+10h]
0x14008951b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089520  nop
0x140089521  lea     rcx, [rbp+var_18]
0x140089525  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x14008952a  mov     eax, ebx
0x14008952c  add     rsp, 48h
0x140089530  pop     rdi
0x140089531  pop     rsi
0x140089532  pop     rbx
0x140089533  pop     rbp
0x140089534  retn
```
