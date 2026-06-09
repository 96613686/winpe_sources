# WxProxyManager::SetProxySettings(tagProxySettings const *,int,int,int *)

- ea: `0x18006e0b0`
- end: `0x18006e327`
- name: `?SetProxySettings@WxProxyManager@@UEAAJPEBUtagProxySettings@@HHPEAH@Z`
- size: `631`
- prototype: `__int64 __fastcall(WxProxyManager *__hidden this, const struct tagProxySettings *, int, int, int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180009070`
- `0x18006e0b0`
- `0x1800a1d10`
- `0x1800cf58c`
- `0x1800db6b0`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e171`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006e171`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006e270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e27e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006e27e`

## pseudocode

```c
__int64 __fastcall WxProxyManager::SetProxySettings(
        WxProxyManager *this,
        const struct tagProxySettings *a2,
        unsigned int a3,
        unsigned int a4,
        int *a5)
{
  int v8; // r13d
  void *v9; // rbx
  int v10; // r12d
  __int128 v11; // xmm1
  __int128 v12; // xmm1
  __int128 v13; // xmm1
  void *v14; // rcx
  int v15; // r14d
  __int64 v16; // rsi
  __int64 v17; // rcx
  int v18; // eax
  int v20; // eax
  int *v21; // [rsp+20h] [rbp-F8h]
  void *v22; // [rsp+30h] [rbp-E8h] BYREF
  unsigned int v23; // [rsp+38h] [rbp-E0h]
  int v24; // [rsp+44h] [rbp-D4h]
  int *v25; // [rsp+48h] [rbp-D0h]
  __int128 v26; // [rsp+50h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+60h] [rbp-B8h]
  __int128 v28; // [rsp+70h] [rbp-A8h]
  __int128 v29; // [rsp+80h] [rbp-98h]
  __int128 v30; // [rsp+90h] [rbp-88h]
  __int128 v31; // [rsp+A0h] [rbp-78h]
  __int128 v32; // [rsp+B0h] [rbp-68h]
  int v33; // [rsp+C0h] [rbp-58h] BYREF

  v25 = a5;
  v23 = a4;
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    LODWORD(v21) = a3;
    WPP_SF_qD(1029, 21, WPP_4c406df889b632584d41ffc9fe5bcada_Traceguids, a2);
  }
  *a5 = 0;
  v8 = 0;
  v24 = 0;
  v9 = 0;
  v33 = 0;
  v10 = 0;
  v22 = 0;
  v11 = *((_OWORD *)a2 + 1);
  v26 = *(_OWORD *)a2;
  v27 = v11;
  v12 = *((_OWORD *)a2 + 3);
  v28 = *((_OWORD *)a2 + 2);
  v29 = v12;
  v13 = *((_OWORD *)a2 + 5);
  v30 = *((_OWORD *)a2 + 4);
  v31 = v13;
  v32 = *((_OWORD *)a2 + 6);
  if ( this != (WxProxyManager *)-72LL )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    v10 = 1;
  }
  if ( *((_DWORD *)this + 34) )
  {
    if ( !a3 )
      goto LABEL_19;
  }
  else
  {
    if ( !a3 )
      goto LABEL_9;
    *((_DWORD *)this + 35) = 0;
  }
  DWORD2(v26) = ++*((_DWORD *)this + 35);
LABEL_9:
  v14 = (void *)*((_QWORD *)this + 15);
  if ( v14 )
  {
    *((_QWORD *)this + 15) = 0;
    CoTaskMemFree(v14);
  }
  if ( (_QWORD)v27 && (v20 = WxNewStringW<WxCoTaskAllocator>((_WORD *)v27, &v22), v9 = v22, v8 = v20, v20 < 0) )
  {
    v24 = 1164;
  }
  else
  {
    v15 = 0;
    v16 = 0;
    LODWORD(v22) = DWORD1(v26);
    while ( 1 )
    {
      if ( (unsigned int)v16 >= *((_DWORD *)this + 16) )
      {
        *v25 = v15;
        v18 = (int)v22;
        *((_QWORD *)this + 15) = v9;
        v9 = 0;
        *((_DWORD *)this + 28) = v18;
        *((_QWORD *)this + 16) = 1;
        *((_DWORD *)this + 34) = a3;
        goto LABEL_19;
      }
      v17 = *((_QWORD *)this + v16 + 4);
      v33 = 0;
      v21 = &v33;
      v8 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v17 + 40LL))(v17, &v26, a3, v23);
      if ( v8 < 0 )
        break;
      if ( v33 )
        v15 = 1;
      v16 = (unsigned int)(v16 + 1);
    }
    v24 = 1175;
  }
LABEL_19:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 22, WPP_4c406df889b632584d41ffc9fe5bcada_Traceguids, (unsigned int)v8, v21);
  if ( v10 && this != (WxProxyManager *)-72LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  if ( v9 )
    CoTaskMemFree(v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18006e0b0  push    rbx
0x18006e0b2  push    rbp
0x18006e0b3  push    rsi
0x18006e0b4  push    rdi
0x18006e0b5  push    r12
0x18006e0b7  push    r13
0x18006e0b9  push    r14
0x18006e0bb  push    r15
0x18006e0bd  sub     rsp, 0D8h
0x18006e0c4  mov     rax, cs:__security_cookie
0x18006e0cb  xor     rax, rsp
0x18006e0ce  mov     [rsp+118h+var_50], rax
0x18006e0d6  mov     r14, [rsp+118h+arg_20]
0x18006e0de  mov     r15d, r8d
0x18006e0e1  mov     [rsp+118h+var_D0], r14
0x18006e0e6  mov     rsi, rdx
0x18006e0e9  mov     [rsp+118h+var_E0], r9d
0x18006e0ee  mov     rdi, rcx
0x18006e0f1  test    byte ptr cs:xmmword_180107A60, 20h
0x18006e0f8  jnz     loc_18006E2E6
0x18006e0fe  xor     edx, edx
0x18006e100  lea     rbp, [rdi+48h]
0x18006e104  mov     [r14], edx
0x18006e107  mov     r13d, edx
0x18006e10a  mov     [rsp+118h+var_D4], edx
0x18006e10e  mov     ebx, edx
0x18006e110  mov     [rsp+118h+var_58], edx
0x18006e117  mov     r12d, edx
0x18006e11a  mov     [rsp+118h+var_E8], rdx
0x18006e11f  movups  xmm0, xmmword ptr [rsi]
0x18006e122  movups  xmm1, xmmword ptr [rsi+10h]
0x18006e126  movaps  [rsp+118h+var_C8], xmm0
0x18006e12b  movaps  [rsp+118h+var_B8], xmm1
0x18006e130  movups  xmm0, xmmword ptr [rsi+20h]
0x18006e134  movups  xmm1, xmmword ptr [rsi+30h]
0x18006e138  movaps  [rsp+118h+var_A8], xmm0
0x18006e13d  movaps  [rsp+118h+var_98], xmm1
0x18006e145  movups  xmm0, xmmword ptr [rsi+40h]
0x18006e149  movups  xmm1, xmmword ptr [rsi+50h]
0x18006e14d  movaps  [rsp+118h+var_88], xmm0
0x18006e155  movaps  [rsp+118h+var_78], xmm1
0x18006e15d  movups  xmm0, xmmword ptr [rsi+60h]
0x18006e161  movaps  [rsp+118h+var_68], xmm0
0x18006e169  test    rbp, rbp
0x18006e16c  jz      short loc_18006E17F
0x18006e16e  mov     rcx, rbp; lpCriticalSection
0x18006e171  call    cs:__imp_EnterCriticalSection
0x18006e177  xor     edx, edx
0x18006e179  mov     r12d, 1
0x18006e17f  cmp     [rdi+88h], ebx
0x18006e185  jnz     loc_18006E2AB
0x18006e18b  test    r15d, r15d
0x18006e18e  jz      short loc_18006E1A6
0x18006e190  mov     [rdi+8Ch], edx
0x18006e196  inc     dword ptr [rdi+8Ch]
0x18006e19c  mov     eax, [rdi+8Ch]
0x18006e1a2  mov     dword ptr [rsp+118h+var_C8+8], eax
0x18006e1a6  mov     rcx, [rdi+78h]; pv
0x18006e1aa  test    rcx, rcx
0x18006e1ad  jz      short loc_18006E1B9
0x18006e1af  mov     [rdi+78h], rdx
0x18006e1b3  call    cs:__imp_CoTaskMemFree
0x18006e1b9  mov     rcx, qword ptr [rsp+118h+var_B8]
0x18006e1be  test    rcx, rcx
0x18006e1c1  jnz     loc_18006E2BF
0x18006e1c7  mov     ecx, dword ptr [rsp+118h+var_C8+4]
0x18006e1cb  xor     r14d, r14d
0x18006e1ce  xor     esi, esi
0x18006e1d0  mov     dword ptr [rsp+118h+var_E8], ecx
0x18006e1d4  cmp     esi, [rdi+40h]
0x18006e1d7  jnb     short loc_18006E22F
0x18006e1d9  mov     rcx, [rdi+rsi*8+20h]
0x18006e1de  lea     rdx, [rsp+118h+var_58]
0x18006e1e6  mov     r9d, [rsp+118h+var_E0]
0x18006e1eb  mov     r8d, r15d
0x18006e1ee  mov     [rsp+118h+var_58], 0
0x18006e1f9  mov     [rsp+118h+var_F8], rdx
0x18006e1fe  lea     rdx, [rsp+118h+var_C8]
0x18006e203  mov     rax, [rcx]
0x18006e206  mov     rax, [rax+28h]
0x18006e20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006e20f  mov     r13d, eax
0x18006e212  test    eax, eax
0x18006e214  js      loc_18006E2B5
0x18006e21a  cmp     [rsp+118h+var_58], 0
0x18006e222  mov     eax, 1
0x18006e227  cmovnz  r14d, eax
0x18006e22b  inc     esi
0x18006e22d  jmp     short loc_18006E1D4
0x18006e22f  mov     rax, [rsp+118h+var_D0]
0x18006e234  mov     [rax], r14d
0x18006e237  mov     eax, dword ptr [rsp+118h+var_E8]
0x18006e23b  mov     [rdi+78h], rbx
0x18006e23f  xor     ebx, ebx
0x18006e241  mov     [rdi+70h], eax
0x18006e244  mov     qword ptr [rdi+80h], 1
0x18006e24f  mov     [rdi+88h], r15d
0x18006e256  test    byte ptr cs:xmmword_180107A60, 20h
0x18006e25d  jnz     loc_18006E309
0x18006e263  test    r12d, r12d
0x18006e266  jz      short loc_18006E276
0x18006e268  test    rbp, rbp
0x18006e26b  jz      short loc_18006E276
0x18006e26d  mov     rcx, rbp; lpCriticalSection
0x18006e270  call    cs:__imp_LeaveCriticalSection
0x18006e276  test    rbx, rbx
0x18006e279  jz      short loc_18006E284
0x18006e27b  mov     rcx, rbx; pv
0x18006e27e  call    cs:__imp_CoTaskMemFree
0x18006e284  mov     eax, r13d
0x18006e287  mov     rcx, [rsp+118h+var_50]
0x18006e28f  xor     rcx, rsp; StackCookie
0x18006e292  call    __security_check_cookie
0x18006e297  add     rsp, 0D8h
0x18006e29e  pop     r15
0x18006e2a0  pop     r14
0x18006e2a2  pop     r13
0x18006e2a4  pop     r12
0x18006e2a6  pop     rdi
0x18006e2a7  pop     rsi
0x18006e2a8  pop     rbp
0x18006e2a9  pop     rbx
0x18006e2aa  retn
0x18006e2ab  test    r15d, r15d
0x18006e2ae  jz      short loc_18006E256
0x18006e2b0  jmp     loc_18006E196
0x18006e2b5  mov     [rsp+118h+var_D4], 497h
0x18006e2bd  jmp     short loc_18006E256
0x18006e2bf  lea     rdx, [rsp+118h+var_E8]
0x18006e2c4  call    ??$WxNewStringW@VWxCoTaskAllocator@@@@YAJPEBGPEAPEAG@Z; WxNewStringW<WxCoTaskAllocator>(ushort const *,ushort * *)
0x18006e2c9  mov     rbx, [rsp+118h+var_E8]
0x18006e2ce  mov     r13d, eax
0x18006e2d1  test    eax, eax
0x18006e2d3  jns     loc_18006E1C7
0x18006e2d9  mov     [rsp+118h+var_D4], 48Ch
0x18006e2e1  jmp     loc_18006E256
0x18006e2e6  mov     edx, 15h
0x18006e2eb  mov     dword ptr [rsp+118h+var_F8], r15d
0x18006e2f0  mov     ecx, 405h
0x18006e2f5  lea     r8, WPP_4c406df889b632584d41ffc9fe5bcada_Traceguids
0x18006e2fc  mov     r9, rsi
0x18006e2ff  call    WPP_SF_qD
0x18006e304  jmp     loc_18006E0FE
0x18006e309  mov     edx, 16h
0x18006e30e  lea     r8, WPP_4c406df889b632584d41ffc9fe5bcada_Traceguids
0x18006e315  mov     ecx, 405h
0x18006e31a  mov     r9d, r13d
0x18006e31d  call    WPP_SF_d
0x18006e322  jmp     loc_18006E263
```
