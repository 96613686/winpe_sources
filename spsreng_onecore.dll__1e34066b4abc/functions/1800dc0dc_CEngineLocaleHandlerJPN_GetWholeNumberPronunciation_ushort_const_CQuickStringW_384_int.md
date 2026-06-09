# CEngineLocaleHandlerJPN::GetWholeNumberPronunciation(ushort const *,CQuickStringW<384> *,int)

- ea: `0x1800dc0dc`
- end: `0x1800dc27b`
- name: `?GetWholeNumberPronunciation@CEngineLocaleHandlerJPN@@QEAAJPEBGPEAV?$CQuickStringW@$0BIA@@@H@Z`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800dde30`

## callees

- `0x1800034b0`
- `0x1800765d0`
- `0x1800c91c4`
- `0x1800dc0dc`
- `0x1800ff490`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc248`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc248`

## pseudocode

```c
__int64 __fastcall CEngineLocaleHandlerJPN::GetWholeNumberPronunciation(__int64 a1, __int16 *a2, __int64 a3, int a4)
{
  int i; // ebx
  __int16 v9; // ax
  __int64 v10; // rax
  __int64 v11; // rax
  LPVOID pv[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h]
  _WORD v15[2]; // [rsp+48h] [rbp-B8h] BYREF
  int v16; // [rsp+4Ch] [rbp-B4h]
  _BYTE v17[784]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[6160]; // [rsp+360h] [rbp+260h] BYREF

  v16 = 59;
  v14 = 0;
  v15[0] = 47;
  *(_OWORD *)pv = 0;
  for ( i = CEngineLocaleHandler::EnsureLookupLexicon((CEngineLocaleHandler *)a1); i >= 0; --a4 )
  {
    if ( !a4 )
      break;
    v9 = *a2;
    if ( !*a2 )
      break;
    v15[1] = *a2;
    if ( v9 != 44 )
    {
      i = (*(__int64 (__fastcall **)(_QWORD, _WORD *, _QWORD, __int64, LPVOID *))(**(_QWORD **)(a1 + 72) + 24LL))(
            *(_QWORD *)(a1 + 72),
            v15,
            *(unsigned __int16 *)(a1 + 40),
            4096,
            pv);
      if ( i < 0 )
        break;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 368LL))(a1, 4096);
      i = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v10 + 48LL))(v10, v14 + 20, v18);
      if ( i < 0 )
        break;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 368LL))(a1, 1);
      i = (*(__int64 (__fastcall **)(__int64, _BYTE *, _BYTE *))(*(_QWORD *)v11 + 40LL))(v11, v18, v17);
      if ( i < 0 )
        break;
      i = CQuickStringW<384>::Append(a3, v17);
    }
    ++a2;
  }
  if ( pv[1] )
    CoTaskMemFree(pv[1]);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x1800dc0dc  mov     [rsp-8+arg_8], rbx
0x1800dc0e1  mov     [rsp-8+arg_18], rsi
0x1800dc0e6  push    rbp
0x1800dc0e7  push    rdi
0x1800dc0e8  push    r12
0x1800dc0ea  push    r14
0x1800dc0ec  push    r15
0x1800dc0ee  lea     rbp, [rsp-1A80h]
0x1800dc0f6  mov     eax, 1B80h
0x1800dc0fb  call    _alloca_probe
0x1800dc100  sub     rsp, rax
0x1800dc103  mov     rax, cs:__security_cookie
0x1800dc10a  xor     rax, rsp
0x1800dc10d  mov     [rbp+1AA0h+var_30], rax
0x1800dc114  xor     eax, eax
0x1800dc116  mov     [rsp+1BA0h+var_1B54], 3Bh ; ';'
0x1800dc11e  mov     [rsp+1BA0h+var_1B60], rax
0x1800dc123  xorps   xmm0, xmm0
0x1800dc126  mov     eax, 2Fh ; '/'
0x1800dc12b  mov     edi, r9d
0x1800dc12e  mov     [rsp+1BA0h+var_1B58], ax
0x1800dc133  mov     r15, r8
0x1800dc136  mov     rsi, rdx
0x1800dc139  mov     r14, rcx
0x1800dc13c  movups  xmmword ptr [rsp+1BA0h+pv], xmm0
0x1800dc141  call    ?EnsureLookupLexicon@CEngineLocaleHandler@@IEAAJXZ; CEngineLocaleHandler::EnsureLookupLexicon(void)
0x1800dc146  mov     ebx, eax
0x1800dc148  test    eax, eax
0x1800dc14a  js      loc_1800DC23E
0x1800dc150  test    edi, edi
0x1800dc152  jz      loc_1800DC23E
0x1800dc158  movzx   eax, word ptr [rsi]
0x1800dc15b  test    ax, ax
0x1800dc15e  jz      loc_1800DC23E
0x1800dc164  mov     [rsp+1BA0h+var_1B56], ax
0x1800dc169  cmp     ax, 2Ch ; ','
0x1800dc16d  jz      loc_1800DC230
0x1800dc173  mov     rcx, [r14+48h]
0x1800dc177  lea     rdx, [rsp+1BA0h+pv]
0x1800dc17c  movzx   r8d, word ptr [r14+28h]
0x1800dc181  mov     r9d, 1000h
0x1800dc187  mov     [rsp+1BA0h+var_1B80], rdx
0x1800dc18c  lea     rdx, [rsp+1BA0h+var_1B58]
0x1800dc191  mov     rax, [rcx]
0x1800dc194  mov     rax, [rax+18h]
0x1800dc198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc19d  mov     ebx, eax
0x1800dc19f  test    eax, eax
0x1800dc1a1  js      loc_1800DC23E
0x1800dc1a7  mov     rax, [r14]
0x1800dc1aa  mov     edx, 1000h
0x1800dc1af  mov     rcx, r14
0x1800dc1b2  mov     rax, [rax+170h]
0x1800dc1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc1be  mov     rdx, [rsp+1BA0h+var_1B60]
0x1800dc1c3  lea     r8, [rbp+1AA0h+var_1840]
0x1800dc1ca  mov     r9, rax
0x1800dc1cd  add     rdx, 14h
0x1800dc1d1  mov     rcx, [rax]
0x1800dc1d4  mov     rax, [rcx+30h]
0x1800dc1d8  mov     rcx, r9
0x1800dc1db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc1e0  mov     ebx, eax
0x1800dc1e2  test    eax, eax
0x1800dc1e4  js      short loc_1800DC23E
0x1800dc1e6  mov     rax, [r14]
0x1800dc1e9  mov     edx, 1
0x1800dc1ee  mov     rcx, r14
0x1800dc1f1  mov     rax, [rax+170h]
0x1800dc1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc1fd  mov     r9, rax
0x1800dc200  lea     r8, [rsp+1BA0h+var_1B50]
0x1800dc205  lea     rdx, [rbp+1AA0h+var_1840]
0x1800dc20c  mov     rcx, [rax]
0x1800dc20f  mov     rax, [rcx+28h]
0x1800dc213  mov     rcx, r9
0x1800dc216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc21b  mov     ebx, eax
0x1800dc21d  test    eax, eax
0x1800dc21f  js      short loc_1800DC23E
0x1800dc221  lea     rdx, [rsp+1BA0h+var_1B50]
0x1800dc226  mov     rcx, r15
0x1800dc229  call    ?Append@?$CQuickStringW@$0BIA@@@QEAAJQEBG@Z; CQuickStringW<384>::Append(ushort const * const)
0x1800dc22e  mov     ebx, eax
0x1800dc230  add     rsi, 2
0x1800dc234  dec     edi
0x1800dc236  test    ebx, ebx
0x1800dc238  jns     loc_1800DC150
0x1800dc23e  mov     rcx, [rsp+1BA0h+pv+8]; pv
0x1800dc243  test    rcx, rcx
0x1800dc246  jz      short loc_1800DC24E
0x1800dc248  call    cs:__imp_CoTaskMemFree
0x1800dc24e  mov     eax, ebx
0x1800dc250  mov     rcx, [rbp+1AA0h+var_30]
0x1800dc257  xor     rcx, rsp; StackCookie
0x1800dc25a  call    __security_check_cookie
0x1800dc25f  lea     r11, [rsp+1BA0h+var_20]
0x1800dc267  mov     rbx, [r11+38h]
0x1800dc26b  mov     rsi, [r11+48h]
0x1800dc26f  mov     rsp, r11
0x1800dc272  pop     r15
0x1800dc274  pop     r14
0x1800dc276  pop     r12
0x1800dc278  pop     rdi
0x1800dc279  pop     rbp
0x1800dc27a  retn
```
