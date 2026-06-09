# CShellResultsListenerEvent::_CatalogStatusWatchProc(void *)

- ea: `0x140032550`
- end: `0x1400326b5`
- name: `?_CatalogStatusWatchProc@CShellResultsListenerEvent@@KAKPEAX@Z`
- size: `357`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140032550`
- `0x14003f17c`
- `0x14009e010`

## import_xrefs

- `KERNEL32!Sleep` at `0x1400326a9`
- `KERNEL32!Sleep` at `0x1400326a9`
- `ole32!CoUninitialize` at `0x14003266c`
- `ole32!CoUninitialize` at `0x14003266c`
- `ole32!CoCreateInstance` at `0x140032598`
- `ole32!CoCreateInstance` at `0x140032598`
- `ole32!CoInitializeEx` at `0x140032565`
- `ole32!CoInitializeEx` at `0x140032565`

## pseudocode

```c
__int64 __fastcall CShellResultsListenerEvent::_CatalogStatusWatchProc(char *Parameter)
{
  int v2; // r14d
  _BYTE *v3; // rbx
  unsigned int v5; // [rsp+60h] [rbp+30h] BYREF
  int v6; // [rsp+68h] [rbp+38h] BYREF
  __int64 v7; // [rsp+70h] [rbp+40h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+48h] BYREF

  if ( CoInitializeEx(0, 0) < 0 )
    return 0;
  ppv = 0;
  if ( CoCreateInstance(&CLSID_CSearchManager, 0, 4u, &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69, &ppv) < 0 )
    goto LABEL_15;
  v7 = 0;
  (*(void (__fastcall **)(LPVOID, const wchar_t *, __int64 *))(*(_QWORD *)ppv + 80LL))(ppv, L"SystemIndex", &v7);
  v2 = 0;
  v3 = Parameter + 88;
  while ( !Parameter[89] )
  {
    v5 = 0;
    v6 = 0;
    (*(void (__fastcall **)(__int64, unsigned int *, int *))(*(_QWORD *)v7 + 48LL))(v7, &v5, &v6);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_10;
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_10cc32c7a2eb32aaa8826d527a7df3a8_Traceguids, v5);
    }
    v3 = Parameter + 88;
LABEL_10:
    if ( v5 )
    {
      if ( *v3 )
      {
        if ( ++v2 == 5 )
        {
LABEL_12:
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)Parameter + 9) + 8LL))(*((_QWORD *)Parameter + 9));
          break;
        }
      }
    }
    else if ( *v3 )
    {
      goto LABEL_12;
    }
    Sleep(0x7D0u);
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
LABEL_15:
  CoUninitialize();
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return 0;
}

```

## disassembly

```asm
0x140032550  push    rbp
0x140032552  push    rbx
0x140032553  push    rsi
0x140032554  push    rdi
0x140032555  push    r14
0x140032557  mov     rbp, rsp
0x14003255a  sub     rsp, 30h
0x14003255e  mov     rdi, rcx
0x140032561  xor     edx, edx; dwCoInit
0x140032563  xor     ecx, ecx; pvReserved
0x140032565  call    cs:__imp_CoInitializeEx
0x14003256b  test    eax, eax
0x14003256d  js      loc_140032689
0x140032573  mov     [rbp+arg_18], 0
0x14003257b  lea     rax, [rbp+arg_18]
0x14003257f  mov     [rsp+30h+ppv], rax; ppv
0x140032584  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x14003258b  xor     edx, edx; pUnkOuter
0x14003258d  lea     r8d, [rdx+4]; dwClsContext
0x140032591  lea     rcx, CLSID_CSearchManager; rclsid
0x140032598  call    cs:__imp_CoCreateInstance
0x14003259e  test    eax, eax
0x1400325a0  js      loc_14003266C
0x1400325a6  mov     [rbp+arg_10], 0
0x1400325ae  mov     rcx, [rbp+arg_18]
0x1400325b2  mov     rax, [rcx]
0x1400325b5  lea     r8, [rbp+arg_10]
0x1400325b9  lea     rdx, aSystemindex; "SystemIndex"
0x1400325c0  mov     rax, [rax+50h]
0x1400325c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400325c9  xor     r14d, r14d
0x1400325cc  lea     rsi, [rdi+58h]
0x1400325d0  mov     rbx, rsi
0x1400325d3  cmp     byte ptr [rdi+59h], 0
0x1400325d7  jnz     short loc_140032656
0x1400325d9  mov     [rbp+arg_0], 0
0x1400325e0  mov     [rbp+arg_8], 0
0x1400325e7  mov     rcx, [rbp+arg_10]
0x1400325eb  mov     rax, [rcx]
0x1400325ee  lea     r8, [rbp+arg_8]
0x1400325f2  lea     rdx, [rbp+arg_0]
0x1400325f6  mov     rax, [rax+30h]
0x1400325fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400325ff  lea     rax, WPP_GLOBAL_Control
0x140032606  mov     rcx, cs:WPP_GLOBAL_Control
0x14003260d  cmp     rcx, rax
0x140032610  jz      short loc_140032637
0x140032612  test    byte ptr [rcx+1Ch], 2
0x140032616  jz      short loc_14003263A
0x140032618  cmp     byte ptr [rcx+19h], 5
0x14003261c  jb      short loc_140032637
0x14003261e  mov     edx, 0Ch
0x140032623  mov     r9d, [rbp+arg_0]
0x140032627  lea     r8, WPP_10cc32c7a2eb32aaa8826d527a7df3a8_Traceguids
0x14003262e  mov     rcx, [rcx+10h]
0x140032632  call    WPP_SF_d
0x140032637  mov     rbx, rsi
0x14003263a  cmp     [rbp+arg_0], 0
0x14003263e  jnz     short loc_140032696
0x140032640  cmp     byte ptr [rbx], 0
0x140032643  jz      short loc_1400326A4
0x140032645  mov     rcx, [rdi+48h]
0x140032649  mov     rax, [rcx]
0x14003264c  mov     rax, [rax+8]
0x140032650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032655  nop
0x140032656  mov     rcx, [rbp+arg_10]
0x14003265a  test    rcx, rcx
0x14003265d  jz      short loc_14003266C
0x14003265f  mov     rax, [rcx]
0x140032662  mov     rax, [rax+10h]
0x140032666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003266b  nop
0x14003266c  call    cs:__imp_CoUninitialize
0x140032672  nop
0x140032673  mov     rcx, [rbp+arg_18]
0x140032677  test    rcx, rcx
0x14003267a  jz      short loc_140032689
0x14003267c  mov     rax, [rcx]
0x14003267f  mov     rax, [rax+10h]
0x140032683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140032688  nop
0x140032689  xor     eax, eax
0x14003268b  add     rsp, 30h
0x14003268f  pop     r14
0x140032691  pop     rdi
0x140032692  pop     rsi
0x140032693  pop     rbx
0x140032694  pop     rbp
0x140032695  retn
0x140032696  cmp     byte ptr [rbx], 0
0x140032699  jz      short loc_1400326A4
0x14003269b  inc     r14d
0x14003269e  cmp     r14d, 5
0x1400326a2  jz      short loc_140032645
0x1400326a4  mov     ecx, 7D0h; dwMilliseconds
0x1400326a9  call    cs:__imp_Sleep
0x1400326af  jmp     loc_1400325D3
```
