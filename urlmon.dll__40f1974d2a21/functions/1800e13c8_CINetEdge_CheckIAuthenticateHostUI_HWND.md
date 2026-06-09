# CINetEdge::CheckIAuthenticateHostUI(HWND__ *)

- ea: `0x1800e13c8`
- end: `0x1800e1680`
- name: `?CheckIAuthenticateHostUI@CINetEdge@@IEAAKPEAUHWND__@@@Z`
- size: `696`
- prototype: `unsigned int __fastcall(CINetEdge *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800e37f0`

## callees

- `0x180008300`
- `0x1800e1074`
- `0x1800e13c8`
- `0x1800e26b8`
- `0x18011c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e149f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e149f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e1477`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e1477`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800e13f9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800e1519`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800e13f9`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800e1519`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e15f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e1631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e165f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e15f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e1631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e165f`
- `WININET!InternetSetOptionW` at `0x1800e1573`
- `WININET!InternetSetOptionW` at `0x1800e15b2`
- `WININET!InternetSetOptionW` at `0x1800e1573`
- `WININET!InternetSetOptionW` at `0x1800e15b2`

## pseudocode

```c
__int64 __fastcall CINetEdge::CheckIAuthenticateHostUI(HINTERNET *this, HWND a2)
{
  unsigned int v5; // r12d
  int v6; // eax
  _WORD *v7; // r14
  int v8; // ebx
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 i; // rax
  __int64 v11; // r9
  _BYTE *v12; // r8
  __int64 v13; // rdi
  __int64 v14; // r9
  _BYTE *v15; // rcx
  __int64 v16; // r9
  __int64 v17; // rax
  __int64 v18; // rdx
  _BYTE *j; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rdi
  LPVOID v23; // [rsp+40h] [rbp-20h] BYREF
  __int64 v24; // [rsp+48h] [rbp-18h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-10h] BYREF
  bool v26; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID lpBuffer; // [rsp+B8h] [rbp+58h] BYREF

  InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
  if ( !byte_18015DE34 )
    return 1223;
  v5 = 0;
  pv = 0;
  lpBuffer = 0;
  v23 = 0;
  v26 = 0;
  if ( this[47] )
  {
    CINetEdge::GetPreviouslySubmittedCredential((CINetEdge *)this, (unsigned __int16 **)&pv);
    v24 = 0;
    v6 = CINetEdge::CheckAuthHeaders((CINetEdge *)this, &v26);
    v7 = pv;
    v8 = v6;
    if ( v6 >= 0 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
      v8 = -2147467263;
      v9 = 0;
      EnterCriticalSection(&g_csDll);
      for ( i = qword_18015E5D8; i; i = *(_QWORD *)(i + 16) )
      {
        if ( *(HWND *)i == a2 )
        {
          v9 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(i + 8);
          break;
        }
      }
      LeaveCriticalSection(&g_csDll);
      if ( !v9 || (v8 = (**v9)(v9, &GUID_ac78490a_ea21_4757_87d2_12bf26030d30, &v24)) != 0 )
      {
        if ( v8 == -2147467263 )
        {
          InitOnceExecuteOnce(&stru_18015EA38, InitOnceDeviceFamily, 0, 0);
          if ( byte_18015DE35 )
            v8 = -2147467259;
        }
      }
      else
      {
        LOBYTE(v11) = v26;
        v8 = (*(__int64 (__fastcall **)(__int64, HINTERNET, _WORD *, __int64, LPVOID *, LPVOID *))(*(_QWORD *)v24 + 24LL))(
               v24,
               this[17],
               v7,
               v11,
               &lpBuffer,
               &v23);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v12 = lpBuffer;
    v13 = -1;
    if ( v8 < 0 )
    {
      v15 = v23;
    }
    else
    {
      if ( lpBuffer )
      {
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)lpBuffer + v14) );
        InternetSetOptionW(this[47], ((_BYTE)this[122] & 1) != 0 ? 43 : 28, lpBuffer, v14 + 1);
        v12 = lpBuffer;
      }
      v15 = v23;
      if ( v23 )
      {
        v16 = -1;
        do
          ++v16;
        while ( *((_WORD *)v23 + v16) );
        InternetSetOptionW(this[47], ((_BYTE)this[122] & 1) != 0 ? 44 : 29, v23, v16 + 1);
        v12 = lpBuffer;
        v15 = v23;
      }
      v5 = 12032;
    }
    if ( v7 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v7[v17] );
      v18 = 2 * v17;
      for ( j = v7; v18; --v18 )
        *j++ = 0;
      CoTaskMemFree(v7);
      v12 = lpBuffer;
      v15 = v23;
    }
    if ( v12 )
    {
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)&v12[2 * v20] );
      v21 = 2 * v20;
      if ( v21 )
      {
        do
        {
          *v12++ = 0;
          --v21;
        }
        while ( v21 );
        v12 = lpBuffer;
      }
      CoTaskMemFree(v12);
      v15 = v23;
    }
    if ( v15 )
    {
      do
        ++v13;
      while ( *(_WORD *)&v15[2 * v13] );
      v22 = 2 * v13;
      if ( v22 )
      {
        do
        {
          *v15++ = 0;
          --v22;
        }
        while ( v22 );
        v15 = v23;
      }
      CoTaskMemFree(v15);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800e13c8  mov     [rsp-38h+arg_0], rbx
0x1800e13cd  push    rbp
0x1800e13ce  push    rsi
0x1800e13cf  push    rdi
0x1800e13d0  push    r12
0x1800e13d2  push    r13
0x1800e13d4  push    r14
0x1800e13d6  push    r15
0x1800e13d8  mov     rbp, rsp
0x1800e13db  sub     rsp, 60h
0x1800e13df  mov     r15, rdx
0x1800e13e2  mov     rsi, rcx
0x1800e13e5  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800e13ec  xor     r9d, r9d; Context
0x1800e13ef  lea     rcx, stru_18015EA38; InitOnce
0x1800e13f6  xor     r8d, r8d; Parameter
0x1800e13f9  call    cs:__imp_InitOnceExecuteOnce
0x1800e13ff  xor     r13d, r13d
0x1800e1402  cmp     cs:byte_18015DE34, r13b
0x1800e1409  jnz     short loc_1800E1415
0x1800e140b  mov     eax, 4C7h
0x1800e1410  jmp     loc_1800E1668
0x1800e1415  mov     r12d, r13d
0x1800e1418  mov     [rbp+pv], r13
0x1800e141c  mov     [rbp+lpBuffer], r13
0x1800e1420  mov     [rbp+var_20], r13
0x1800e1424  mov     [rbp+arg_10], r13b
0x1800e1428  cmp     [rsi+178h], r13
0x1800e142f  jz      loc_1800E1665
0x1800e1435  lea     rdx, [rbp+pv]; unsigned __int16 **
0x1800e1439  mov     rcx, rsi; this
0x1800e143c  call    ?GetPreviouslySubmittedCredential@CINetEdge@@IEAAHPEAPEAG@Z; CINetEdge::GetPreviouslySubmittedCredential(ushort * *)
0x1800e1441  lea     rdx, [rbp+arg_10]; bool *
0x1800e1445  mov     [rbp+var_18], r13
0x1800e1449  mov     rcx, rsi; this
0x1800e144c  call    ?CheckAuthHeaders@CINetEdge@@IEAAJPEA_N@Z; CINetEdge::CheckAuthHeaders(bool *)
0x1800e1451  mov     r14, [rbp+pv]
0x1800e1455  mov     ebx, eax
0x1800e1457  test    eax, eax
0x1800e1459  js      loc_1800E152C
0x1800e145f  lea     rcx, [rbp+var_18]
0x1800e1463  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e1468  lea     rcx, ?g_csDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800e146f  mov     ebx, 80004001h
0x1800e1474  mov     rdi, r13
0x1800e1477  call    cs:__imp_EnterCriticalSection
0x1800e147d  mov     rax, cs:qword_18015E5D8
0x1800e1484  test    rax, rax
0x1800e1487  jz      short loc_1800E1498
0x1800e1489  cmp     [rax], r15
0x1800e148c  jz      short loc_1800E1494
0x1800e148e  mov     rax, [rax+10h]
0x1800e1492  jmp     short loc_1800E1484
0x1800e1494  mov     rdi, [rax+8]
0x1800e1498  lea     rcx, ?g_csDll@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800e149f  call    cs:__imp_LeaveCriticalSection
0x1800e14a5  test    rdi, rdi
0x1800e14a8  jz      short loc_1800E14FD
0x1800e14aa  mov     rax, [rdi]
0x1800e14ad  lea     r8, [rbp+var_18]
0x1800e14b1  lea     rdx, _GUID_ac78490a_ea21_4757_87d2_12bf26030d30
0x1800e14b8  mov     rcx, rdi
0x1800e14bb  mov     rax, [rax]
0x1800e14be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e14c3  mov     ebx, eax
0x1800e14c5  test    eax, eax
0x1800e14c7  jnz     short loc_1800E14FD
0x1800e14c9  mov     rcx, [rbp+var_18]
0x1800e14cd  lea     rdx, [rbp+var_20]
0x1800e14d1  mov     r9b, [rbp+arg_10]
0x1800e14d5  mov     r8, r14
0x1800e14d8  mov     [rsp+60h+var_38], rdx
0x1800e14dd  lea     rdx, [rbp+lpBuffer]
0x1800e14e1  mov     [rsp+60h+var_40], rdx
0x1800e14e6  mov     rax, [rcx]
0x1800e14e9  mov     rdx, [rsi+88h]
0x1800e14f0  mov     rax, [rax+18h]
0x1800e14f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e14f9  mov     ebx, eax
0x1800e14fb  jmp     short loc_1800E152C
0x1800e14fd  cmp     ebx, 80004001h
0x1800e1503  jnz     short loc_1800E152C
0x1800e1505  xor     r9d, r9d; Context
0x1800e1508  lea     rdx, ?InitOnceDeviceFamily@@YAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800e150f  xor     r8d, r8d; Parameter
0x1800e1512  lea     rcx, stru_18015EA38; InitOnce
0x1800e1519  call    cs:__imp_InitOnceExecuteOnce
0x1800e151f  cmp     cs:byte_18015DE35, r13b
0x1800e1526  lea     eax, [rbx+4]
0x1800e1529  cmovnz  ebx, eax
0x1800e152c  lea     rcx, [rbp+var_18]
0x1800e1530  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e1535  mov     r8, [rbp+lpBuffer]; lpBuffer
0x1800e1539  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800e153d  test    ebx, ebx
0x1800e153f  js      loc_1800E15C8
0x1800e1545  test    r8, r8
0x1800e1548  jz      short loc_1800E157D
0x1800e154a  mov     r9, rdi
0x1800e154d  inc     r9
0x1800e1550  cmp     [r8+r9*2], r13w
0x1800e1555  jnz     short loc_1800E154D
0x1800e1557  mov     al, [rsi+3D0h]
0x1800e155d  inc     r9d; dwBufferLength
0x1800e1560  mov     rcx, [rsi+178h]; hInternet
0x1800e1567  and     al, 1
0x1800e1569  neg     al
0x1800e156b  sbb     edx, edx
0x1800e156d  and     edx, 0Fh
0x1800e1570  add     edx, 1Ch; dwOption
0x1800e1573  call    cs:__imp_InternetSetOptionW
0x1800e1579  mov     r8, [rbp+lpBuffer]
0x1800e157d  mov     rcx, [rbp+var_20]
0x1800e1581  test    rcx, rcx
0x1800e1584  jz      short loc_1800E15C0
0x1800e1586  mov     r9, rdi
0x1800e1589  inc     r9
0x1800e158c  cmp     [rcx+r9*2], r13w
0x1800e1591  jnz     short loc_1800E1589
0x1800e1593  mov     al, [rsi+3D0h]
0x1800e1599  inc     r9d; dwBufferLength
0x1800e159c  and     al, 1
0x1800e159e  mov     r8, rcx; lpBuffer
0x1800e15a1  mov     rcx, [rsi+178h]; hInternet
0x1800e15a8  neg     al
0x1800e15aa  sbb     edx, edx
0x1800e15ac  and     edx, 0Fh
0x1800e15af  add     edx, 1Dh; dwOption
0x1800e15b2  call    cs:__imp_InternetSetOptionW
0x1800e15b8  mov     r8, [rbp+lpBuffer]
0x1800e15bc  mov     rcx, [rbp+var_20]
0x1800e15c0  mov     r12d, 2F00h
0x1800e15c6  jmp     short loc_1800E15CC
0x1800e15c8  mov     rcx, [rbp+var_20]
0x1800e15cc  test    r14, r14
0x1800e15cf  jz      short loc_1800E1607
0x1800e15d1  mov     rax, rdi
0x1800e15d4  inc     rax
0x1800e15d7  cmp     [r14+rax*2], r13w
0x1800e15dc  jnz     short loc_1800E15D4
0x1800e15de  lea     rdx, [rax+rax]
0x1800e15e2  mov     rax, r14
0x1800e15e5  test    rdx, rdx
0x1800e15e8  jz      short loc_1800E15F6
0x1800e15ea  mov     [rax], r13b
0x1800e15ed  inc     rax
0x1800e15f0  sub     rdx, 1
0x1800e15f4  jnz     short loc_1800E15EA
0x1800e15f6  mov     rcx, r14; pv
0x1800e15f9  call    cs:__imp_CoTaskMemFree
0x1800e15ff  mov     r8, [rbp+lpBuffer]
0x1800e1603  mov     rcx, [rbp+var_20]
0x1800e1607  test    r8, r8
0x1800e160a  jz      short loc_1800E163B
0x1800e160c  mov     rax, rdi
0x1800e160f  inc     rax
0x1800e1612  cmp     [r8+rax*2], r13w
0x1800e1617  jnz     short loc_1800E160F
0x1800e1619  add     rax, rax
0x1800e161c  jz      short loc_1800E162E
0x1800e161e  mov     [r8], r13b
0x1800e1621  inc     r8
0x1800e1624  sub     rax, 1
0x1800e1628  jnz     short loc_1800E161E
0x1800e162a  mov     r8, [rbp+lpBuffer]
0x1800e162e  mov     rcx, r8; pv
0x1800e1631  call    cs:__imp_CoTaskMemFree
0x1800e1637  mov     rcx, [rbp+var_20]
0x1800e163b  test    rcx, rcx
0x1800e163e  jz      short loc_1800E1665
0x1800e1640  inc     rdi
0x1800e1643  cmp     [rcx+rdi*2], r13w
0x1800e1648  jnz     short loc_1800E1640
0x1800e164a  add     rdi, rdi
0x1800e164d  jz      short loc_1800E165F
0x1800e164f  mov     [rcx], r13b
0x1800e1652  inc     rcx
0x1800e1655  sub     rdi, 1
0x1800e1659  jnz     short loc_1800E164F
0x1800e165b  mov     rcx, [rbp+var_20]; pv
0x1800e165f  call    cs:__imp_CoTaskMemFree
0x1800e1665  mov     eax, r12d
0x1800e1668  mov     rbx, [rsp+60h+arg_0]
0x1800e1670  add     rsp, 60h
0x1800e1674  pop     r15
0x1800e1676  pop     r14
0x1800e1678  pop     r13
0x1800e167a  pop     r12
0x1800e167c  pop     rdi
0x1800e167d  pop     rsi
0x1800e167e  pop     rbp
0x1800e167f  retn
```
