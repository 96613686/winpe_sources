# CShellQuery::_NotifyIndexingItems(IRowset *,IIndexListener *,ulong *)

- ea: `0x1400890e0`
- end: `0x1400892d3`
- name: `?_NotifyIndexingItems@CShellQuery@@IEAAJPEAUIRowset@@PEAVIIndexListener@@PEAK@Z`
- size: `499`
- prototype: `__int64 __fastcall(CShellQuery *this, IUnknown *, struct IIndexListener *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140084cc8`

## callees

- `0x14000cb74`
- `0x140024688`
- `0x140047798`
- `0x140083574`
- `0x1400890e0`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x1400891c3`
- `KERNEL32!CreateThread` at `0x1400891c3`
- `KERNEL32!GetLastError` at `0x1400891d2`
- `KERNEL32!GetLastError` at `0x1400891d2`
- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x140089210`
- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x14008927a`
- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x140089210`
- `SHLWAPI!__imp_ConnectToConnectionPoint` at `0x14008927a`

## pseudocode

```c
__int64 __fastcall CShellQuery::_NotifyIndexingItems(
        CShellQuery *this,
        IUnknown *a2,
        struct IIndexListener *a3,
        unsigned int *a4)
{
  int v7; // ebx
  LPVOID v8; // rdi
  struct IUnknown *v9; // rdx
  HANDLE Thread; // rax
  signed int LastError; // eax
  int v13; // [rsp+30h] [rbp-10h] BYREF
  struct IUnknown *v14; // [rsp+38h] [rbp-8h] BYREF
  LPVOID lpParameter; // [rsp+70h] [rbp+30h] BYREF
  int v16; // [rsp+78h] [rbp+38h] BYREF

  lpParameter = this;
  v14 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_10cc32c7a2eb32aaa8826d527a7df3a8_Traceguids);
  }
  v7 = ((__int64 (__fastcall *)(IUnknown *, GUID *, struct IUnknown **))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_42811652_079d_481b_87a2_09a69ecc5f44,
         &v14);
  if ( v7 >= 0 )
  {
    lpParameter = 0;
    v7 = ATL::CComObject<CShellResultsListenerEvent>::CreateInstance(&lpParameter);
    if ( v7 >= 0 )
    {
      v8 = lpParameter;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpParameter + 8LL))(lpParameter);
      v9 = v14;
      *((_QWORD *)v8 + 9) = a3;
      if ( *((struct IUnknown **)v8 + 10) != v9 )
        ATL::AtlComPtrAssign((struct IUnknown **)v8 + 10, v9);
      Thread = CreateThread(
                 0,
                 0,
                 (LPTHREAD_START_ROUTINE)CShellResultsListenerEvent::_CatalogStatusWatchProc,
                 v8,
                 0,
                 (LPDWORD)v8 + 26);
      *((_QWORD *)v8 + 12) = Thread;
      if ( Thread )
        goto LABEL_13;
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 >= 0 )
      {
LABEL_13:
        v7 = ConnectToConnectionPoint((IUnknown *)v8, &GUID_1551aea5_5d66_4b11_86f5_d5634cb211b9, 1, a2, a4, 0);
        if ( v7 >= 0 )
        {
          v13 = 0;
          LODWORD(lpParameter) = 0;
          v16 = 0;
          ((void (__fastcall *)(struct IUnknown *, int *, LPVOID *, int *))v14->lpVtbl[1].Release)(
            v14,
            &v13,
            &lpParameter,
            &v16);
          if ( (_DWORD)lpParameter || v16 )
          {
            v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64))v14->lpVtbl[1].QueryInterface)(
                   v14,
                   2,
                   1000);
          }
          else
          {
            ConnectToConnectionPoint(0, &GUID_1551aea5_5d66_4b11_86f5_d5634cb211b9, 0, a2, a4, 0);
            v7 = -2147023728;
          }
        }
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    }
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400890e0  mov     [rsp-28h+arg_10], rbx
0x1400890e5  mov     [rsp-28h+lpParameter], rcx
0x1400890ea  push    rbp
0x1400890eb  push    rsi
0x1400890ec  push    rdi
0x1400890ed  push    r14
0x1400890ef  push    r15
0x1400890f1  mov     rbp, rsp
0x1400890f4  sub     rsp, 40h
0x1400890f8  mov     r14, r9
0x1400890fb  mov     r15, r8
0x1400890fe  mov     rsi, rdx
0x140089101  mov     [rbp+var_8], 0
0x140089109  lea     rax, WPP_GLOBAL_Control
0x140089110  mov     rcx, cs:WPP_GLOBAL_Control
0x140089117  cmp     rcx, rax
0x14008911a  jz      short loc_14008913D
0x14008911c  test    byte ptr [rcx+1Ch], 2
0x140089120  jz      short loc_14008913D
0x140089122  cmp     byte ptr [rcx+19h], 5
0x140089126  jb      short loc_14008913D
0x140089128  mov     edx, 0Eh
0x14008912d  lea     r8, WPP_10cc32c7a2eb32aaa8826d527a7df3a8_Traceguids
0x140089134  mov     rcx, [rcx+10h]
0x140089138  call    WPP_SF_
0x14008913d  mov     rax, [rsi]
0x140089140  lea     r8, [rbp+var_8]
0x140089144  lea     rdx, _GUID_42811652_079d_481b_87a2_09a69ecc5f44
0x14008914b  mov     rcx, rsi
0x14008914e  mov     rax, [rax]
0x140089151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089156  mov     ebx, eax
0x140089158  test    eax, eax
0x14008915a  js      loc_1400892B4
0x140089160  mov     [rbp+lpParameter], 0
0x140089168  lea     rcx, [rbp+lpParameter]
0x14008916c  call    ?CreateInstance@?$CComObject@VCShellResultsListenerEvent@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CShellResultsListenerEvent>::CreateInstance(ATL::CComObject<CShellResultsListenerEvent> * *)
0x140089171  mov     ebx, eax
0x140089173  test    eax, eax
0x140089175  js      loc_1400892B4
0x14008917b  mov     rdi, [rbp+lpParameter]
0x14008917f  mov     rax, [rdi]
0x140089182  mov     rcx, rdi
0x140089185  mov     rax, [rax+8]
0x140089189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14008918e  mov     rdx, [rbp+var_8]; struct IUnknown *
0x140089192  mov     [rdi+48h], r15
0x140089196  lea     rcx, [rdi+50h]; struct IUnknown **
0x14008919a  cmp     [rcx], rdx
0x14008919d  jz      short loc_1400891A4
0x14008919f  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1400891a4  lea     rax, [rdi+68h]
0x1400891a8  mov     [rsp+40h+lpThreadId], rax; lpThreadId
0x1400891ad  mov     [rsp+40h+dwCreationFlags], 0; dwCreationFlags
0x1400891b5  mov     r9, rdi; lpParameter
0x1400891b8  lea     r8, ?_CatalogStatusWatchProc@CShellResultsListenerEvent@@KAKPEAX@Z; lpStartAddress
0x1400891bf  xor     edx, edx; dwStackSize
0x1400891c1  xor     ecx, ecx; lpThreadAttributes
0x1400891c3  call    cs:__imp_CreateThread
0x1400891c9  mov     [rdi+60h], rax
0x1400891cd  test    rax, rax
0x1400891d0  jnz     short loc_1400891EF
0x1400891d2  call    cs:__imp_GetLastError
0x1400891d8  mov     ebx, eax
0x1400891da  test    eax, eax
0x1400891dc  jle     short loc_1400891E7
0x1400891de  movzx   ebx, ax
0x1400891e1  or      ebx, 80070000h
0x1400891e7  test    ebx, ebx
0x1400891e9  js      loc_1400892A4
0x1400891ef  mov     [rsp+40h+lpThreadId], 0; ppcpOut
0x1400891f8  mov     qword ptr [rsp+40h+dwCreationFlags], r14; pdwCookie
0x1400891fd  mov     r9, rsi; punkTarget
0x140089200  mov     r8d, 1; fConnect
0x140089206  lea     rdx, _GUID_1551aea5_5d66_4b11_86f5_d5634cb211b9; riidEvent
0x14008920d  mov     rcx, rdi; punk
0x140089210  call    cs:__imp_ConnectToConnectionPoint
0x140089216  mov     ebx, eax
0x140089218  test    eax, eax
0x14008921a  js      loc_1400892A4
0x140089220  mov     [rbp+var_10], 0
0x140089227  mov     dword ptr [rbp+lpParameter], 0
0x14008922e  mov     [rbp+arg_8], 0
0x140089235  mov     rcx, [rbp+var_8]
0x140089239  mov     rax, [rcx]
0x14008923c  lea     r9, [rbp+arg_8]
0x140089240  lea     r8, [rbp+lpParameter]
0x140089244  lea     rdx, [rbp+var_10]
0x140089248  mov     rax, [rax+28h]
0x14008924c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140089251  cmp     dword ptr [rbp+lpParameter], 0
0x140089255  jnz     short loc_140089287
0x140089257  cmp     [rbp+arg_8], 0
0x14008925b  jnz     short loc_140089287
0x14008925d  mov     [rsp+40h+lpThreadId], 0; ppcpOut
0x140089266  mov     qword ptr [rsp+40h+dwCreationFlags], r14; pdwCookie
0x14008926b  mov     r9, rsi; punkTarget
0x14008926e  xor     r8d, r8d; fConnect
0x140089271  lea     rdx, _GUID_1551aea5_5d66_4b11_86f5_d5634cb211b9; riidEvent
0x140089278  xor     ecx, ecx; punk
0x14008927a  call    cs:__imp_ConnectToConnectionPoint
0x140089280  mov     ebx, 80070490h
0x140089285  jmp     short loc_1400892A4
0x140089287  mov     rcx, [rbp+var_8]
0x14008928b  mov     rax, [rcx]
0x14008928e  mov     edx, 2
0x140089293  mov     r8d, 3E8h
0x140089299  mov     rax, [rax+18h]
0x14008929d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400892a2  mov     ebx, eax
0x1400892a4  mov     rax, [rdi]
0x1400892a7  mov     rcx, rdi
0x1400892aa  mov     rax, [rax+10h]
0x1400892ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400892b3  nop
0x1400892b4  lea     rcx, [rbp+var_8]
0x1400892b8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400892bd  mov     eax, ebx
0x1400892bf  mov     rbx, [rsp+40h+arg_10]
0x1400892c7  add     rsp, 40h
0x1400892cb  pop     r15
0x1400892cd  pop     r14
0x1400892cf  pop     rdi
0x1400892d0  pop     rsi
0x1400892d1  pop     rbp
0x1400892d2  retn
```
