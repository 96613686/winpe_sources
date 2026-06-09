# StaticProxyResolver::GetProxyForUrl(ulong,tagProxyResolveUrl const *,ulong *,IUnknown *,IGetProxyForUrlCompletion *,IProxyResult * *)

- ea: `0x1800720a0`
- end: `0x1800723d0`
- name: `?GetProxyForUrl@StaticProxyResolver@@UEAAJKPEBUtagProxyResolveUrl@@PEAKPEAUIUnknown@@PEAUIGetProxyForUrlCompletion@@PEAPEAUIProxyResult@@@Z`
- size: `816`
- prototype: `__int64 __fastcall(StaticProxyResolver *__hidden this, unsigned int, const struct tagProxyResolveUrl *, unsigned int *, struct IUnknown *, struct IGetProxyForUrlCompletion *, struct IProxyResult **)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800720a0`
- `0x1800723d8`
- `0x180072410`
- `0x180072598`
- `0x18007278c`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800d06a4`
- `0x1800db6b0`
- `0x1800dcc10`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072129`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180072129`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072152`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072264`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072152`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072264`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072178`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180072178`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800721f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800721f5`

## pseudocode

```c
__int64 __fastcall StaticProxyResolver::GetProxyForUrl(
        StaticProxyResolver *this,
        char a2,
        const struct tagProxyResolveUrl *a3,
        unsigned int *a4,
        struct IUnknown *a5,
        struct IGetProxyForUrlCompletion *a6,
        struct IProxyResult **a7)
{
  struct IProxyResult *v10; // rdi
  int ProxyHostName; // r15d
  unsigned int v12; // ebx
  unsigned int v13; // esi
  _OWORD *v14; // rax
  StaticProxyResult *v15; // rax
  int IsHostInBypassList; // ebx
  void *v17; // rcx
  int InstanceProxy; // eax
  int *v20; // [rsp+20h] [rbp-60h]
  int v21; // [rsp+50h] [rbp-30h] BYREF
  int v22; // [rsp+54h] [rbp-2Ch]
  int v23; // [rsp+58h] [rbp-28h]
  struct IProxyResult *v24; // [rsp+60h] [rbp-20h]
  unsigned __int16 v25; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v26; // [rsp+6Ch] [rbp-14h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-10h] BYREF

  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qDqqqqq(
      (_DWORD)a6,
      a2,
      (_DWORD)a3,
      (_DWORD)this,
      a2,
      (__int64)a3,
      (__int64)a4,
      (__int64)a5,
      (__int64)a6,
      (__int64)a7);
  v22 = 0;
  v10 = 0;
  v23 = 0;
  v21 = 0;
  v24 = 0;
  pv = 0;
  v26 = 0;
  v25 = 0;
  if ( (a2 & 4) == 0 )
  {
    IsHostInBypassList = -2147023728;
    v22 = 654;
    goto LABEL_17;
  }
  ProxyHostName = 0;
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_S(1029, 17, WPP_bbb471cff1993fcc2367af86668fb1d1_Traceguids, *((_QWORD *)a3 + 1));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *((_DWORD *)this + 20) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      v20 = &v21;
      IsHostInBypassList = StaticProxyResolver::IsHostInBypassList(
                             this,
                             *((unsigned int *)a3 + 6),
                             *((_QWORD *)a3 + 1),
                             *((unsigned __int16 *)a3 + 14));
      if ( IsHostInBypassList < 0 )
      {
        v22 = 686;
        goto LABEL_29;
      }
      if ( !v23 )
      {
        v20 = (int *)&v25;
        ProxyHostName = PROXY_SERVER_LIST::GetProxyHostName(*((_QWORD *)this + 2), *((unsigned int *)a3 + 6), &v26, &pv);
      }
    }
    if ( !*((_DWORD *)this + 18) || ProxyHostName )
      goto LABEL_10;
    v22 = 701;
LABEL_28:
    IsHostInBypassList = -2147023728;
LABEL_29:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    goto LABEL_17;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_(1029, 18, WPP_bbb471cff1993fcc2367af86668fb1d1_Traceguids);
  if ( *((_DWORD *)this + 18) )
  {
    v22 = 671;
    goto LABEL_28;
  }
LABEL_10:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v12 = *((_DWORD *)this + 22);
  v13 = *((_DWORD *)this + 19);
  if ( ProxyHostName )
  {
    v20 = (int *)pv;
    InstanceProxy = StaticProxyResult::CreateInstanceProxy(v13, v12, v26, v25);
    v10 = v24;
    IsHostInBypassList = InstanceProxy;
    if ( InstanceProxy < 0 )
    {
      v22 = 715;
      goto LABEL_17;
    }
  }
  else
  {
    HIDWORD(v24) = 0;
    v14 = HeapAlloc(g_hWxProcessHeap, 0, 0x28u);
    if ( !v14
      || (*v14 = 0,
          v14[1] = 0,
          *((_QWORD *)v14 + 4) = 0,
          (v15 = StaticProxyResult::StaticProxyResult((StaticProxyResult *)v14)) == 0) )
    {
      HIDWORD(v24) = 343;
      IsHostInBypassList = -2147024882;
      v22 = 722;
      goto LABEL_17;
    }
    v10 = v15;
    *((_DWORD *)v15 + 8) = v21;
    *((_DWORD *)v15 + 3) = v13;
    *((_DWORD *)v15 + 6) = 0;
    *((_DWORD *)v15 + 9) = v12;
    *((_WORD *)v15 + 14) = 0;
    IsHostInBypassList = 0;
  }
  if ( v10 )
    (*(void (__fastcall **)(struct IProxyResult *))(*(_QWORD *)v10 + 8LL))(v10);
  *a7 = v10;
LABEL_17:
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 19, WPP_bbb471cff1993fcc2367af86668fb1d1_Traceguids, (unsigned int)IsHostInBypassList, v20);
  v17 = pv;
  if ( pv )
  {
    pv = 0;
    CoTaskMemFree(v17);
  }
  if ( v10 )
    (*(void (__fastcall **)(struct IProxyResult *))(*(_QWORD *)v10 + 16LL))(v10);
  return (unsigned int)IsHostInBypassList;
}

```

## disassembly

```asm
0x1800720a0  mov     [rsp-38h+arg_8], rbx
0x1800720a5  push    rbp
0x1800720a6  push    rsi
0x1800720a7  push    rdi
0x1800720a8  push    r12
0x1800720aa  push    r13
0x1800720ac  push    r14
0x1800720ae  push    r15
0x1800720b0  mov     rbp, rsp
0x1800720b3  sub     rsp, 80h
0x1800720ba  mov     rax, cs:__security_cookie
0x1800720c1  xor     rax, rsp
0x1800720c4  mov     [rbp+var_8], rax
0x1800720c8  mov     rax, [rbp+arg_20]
0x1800720cc  mov     rsi, rcx
0x1800720cf  mov     rcx, [rbp+arg_28]
0x1800720d3  mov     r14, r8
0x1800720d6  mov     r13, [rbp+arg_30]
0x1800720da  mov     ebx, edx
0x1800720dc  test    byte ptr cs:xmmword_180107A60, 20h
0x1800720e3  jnz     loc_180072336
0x1800720e9  xor     r12d, r12d
0x1800720ec  mov     [rbp+var_2C], r12d
0x1800720f0  mov     edi, r12d
0x1800720f3  mov     [rbp+var_28], r12d
0x1800720f7  mov     [rbp+var_30], r12d
0x1800720fb  mov     [rbp+var_20], r12
0x1800720ff  mov     [rbp+pv], r12
0x180072103  mov     [rbp+var_14], r12d
0x180072107  mov     [rbp+var_18], r12w
0x18007210c  test    bl, 4
0x18007210f  jz      loc_18007226F
0x180072115  mov     r15d, r12d
0x180072118  test    byte ptr cs:xmmword_180107A60, 20h
0x18007211f  jnz     loc_180072360
0x180072125  lea     rcx, [rsi+20h]; lpCriticalSection
0x180072129  call    cs:__imp_EnterCriticalSection
0x18007212f  cmp     [rsi+50h], edi
0x180072132  jnz     loc_180072238
0x180072138  test    byte ptr cs:xmmword_180107A60, 20h
0x18007213f  jnz     loc_18007237F
0x180072145  cmp     [rsi+48h], edi
0x180072148  jnz     loc_18007239A
0x18007214e  lea     rcx, [rsi+20h]; lpCriticalSection
0x180072152  call    cs:__imp_LeaveCriticalSection
0x180072158  mov     ebx, [rsi+58h]
0x18007215b  mov     esi, [rsi+4Ch]
0x18007215e  test    r15d, r15d
0x180072161  jnz     loc_180072280
0x180072167  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18007216e  lea     r8d, [r15+28h]; dwBytes
0x180072172  xor     edx, edx; dwFlags
0x180072174  mov     dword ptr [rbp+var_20+4], r12d
0x180072178  call    cs:__imp_HeapAlloc
0x18007217e  test    rax, rax
0x180072181  jz      loc_1800722BE
0x180072187  xorps   xmm0, xmm0
0x18007218a  xor     ecx, ecx
0x18007218c  movups  xmmword ptr [rax], xmm0
0x18007218f  movups  xmmword ptr [rax+10h], xmm0
0x180072193  mov     [rax+20h], rcx
0x180072197  mov     rcx, rax; this
0x18007219a  call    ??0StaticProxyResult@@AEAA@XZ; StaticProxyResult::StaticProxyResult(void)
0x18007219f  test    rax, rax
0x1800721a2  jz      loc_1800722BE
0x1800721a8  mov     ecx, [rbp+var_30]
0x1800721ab  mov     rdi, rax
0x1800721ae  mov     [rax+20h], ecx
0x1800721b1  mov     [rax+0Ch], esi
0x1800721b4  mov     [rax+18h], r12d
0x1800721b8  mov     [rax+24h], ebx
0x1800721bb  mov     [rax+1Ch], r12w
0x1800721c0  mov     ebx, r12d
0x1800721c3  test    rdi, rdi
0x1800721c6  jz      short loc_1800721D7
0x1800721c8  mov     rax, [rdi]
0x1800721cb  mov     rcx, rdi
0x1800721ce  mov     rax, [rax+8]
0x1800721d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721d7  mov     [r13+0], rdi
0x1800721db  test    byte ptr cs:xmmword_180107A60, 20h
0x1800721e2  jnz     loc_1800723B2
0x1800721e8  mov     rcx, [rbp+pv]; pv
0x1800721ec  test    rcx, rcx
0x1800721ef  jz      short loc_1800721FB
0x1800721f1  mov     [rbp+pv], r12
0x1800721f5  call    cs:__imp_CoTaskMemFree
0x1800721fb  test    rdi, rdi
0x1800721fe  jz      short loc_18007220F
0x180072200  mov     rdx, [rdi]
0x180072203  mov     rcx, rdi
0x180072206  mov     rax, [rdx+10h]
0x18007220a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007220f  mov     eax, ebx
0x180072211  mov     rcx, [rbp+var_8]
0x180072215  xor     rcx, rsp; StackCookie
0x180072218  call    __security_check_cookie
0x18007221d  mov     rbx, [rsp+80h+arg_8]
0x180072225  add     rsp, 80h
0x18007222c  pop     r15
0x18007222e  pop     r14
0x180072230  pop     r13
0x180072232  pop     r12
0x180072234  pop     rdi
0x180072235  pop     rsi
0x180072236  pop     rbp
0x180072237  retn
0x180072238  cmp     [rsi+10h], rdi
0x18007223c  jnz     loc_1800722D6
0x180072242  cmp     [rsi+48h], edi
0x180072245  jz      loc_18007214E
0x18007224b  test    r15d, r15d
0x18007224e  jnz     loc_18007214E
0x180072254  mov     [rbp+var_2C], 2BDh
0x18007225b  mov     ebx, 80070490h
0x180072260  lea     rcx, [rsi+20h]; lpCriticalSection
0x180072264  call    cs:__imp_LeaveCriticalSection
0x18007226a  jmp     loc_1800721DB
0x18007226f  mov     ebx, 80070490h
0x180072274  mov     [rbp+var_2C], 28Eh
0x18007227b  jmp     loc_1800721DB
0x180072280  movzx   r9d, [rbp+var_18]
0x180072285  lea     rax, [rbp+var_20]
0x180072289  mov     r8d, [rbp+var_14]
0x18007228d  mov     edx, ebx
0x18007228f  mov     [rsp+80h+var_58], rax
0x180072294  mov     ecx, esi
0x180072296  mov     rax, [rbp+pv]
0x18007229a  mov     [rsp+80h+var_60], rax
0x18007229f  call    ?CreateInstanceProxy@StaticProxyResult@@SAJKW4ProxyResultConfigType@@W4ProxyResolveScheme@@GPEBGPEAPEAV1@@Z; StaticProxyResult::CreateInstanceProxy(ulong,ProxyResultConfigType,ProxyResolveScheme,ushort,ushort const *,StaticProxyResult * *)
0x1800722a4  mov     rdi, [rbp+var_20]
0x1800722a8  mov     ebx, eax
0x1800722aa  test    eax, eax
0x1800722ac  jns     loc_1800721C3
0x1800722b2  mov     [rbp+var_2C], 2CBh
0x1800722b9  jmp     loc_1800721DB
0x1800722be  mov     dword ptr [rbp+var_20+4], 157h
0x1800722c5  mov     ebx, 8007000Eh
0x1800722ca  mov     [rbp+var_2C], 2D2h
0x1800722d1  jmp     loc_1800721DB
0x1800722d6  movzx   r9d, word ptr [r14+1Ch]
0x1800722db  lea     rax, [rbp+var_28]
0x1800722df  mov     r8, [r14+8]
0x1800722e3  mov     rcx, rsi
0x1800722e6  mov     edx, [r14+18h]
0x1800722ea  mov     [rsp+80h+var_58], rax
0x1800722ef  lea     rax, [rbp+var_30]
0x1800722f3  mov     [rsp+80h+var_60], rax
0x1800722f8  call    ?IsHostInBypassList@StaticProxyResolver@@AEAAJW4ProxyResolveScheme@@PEBGGPEAH2@Z; StaticProxyResolver::IsHostInBypassList(ProxyResolveScheme,ushort const *,ushort,int *,int *)
0x1800722fd  mov     ebx, eax
0x1800722ff  test    eax, eax
0x180072301  js      loc_1800723A6
0x180072307  cmp     [rbp+var_28], edi
0x18007230a  jnz     loc_180072242
0x180072310  mov     edx, [r14+18h]
0x180072314  lea     rax, [rbp+var_18]
0x180072318  mov     rcx, [rsi+10h]
0x18007231c  lea     r9, [rbp+pv]
0x180072320  lea     r8, [rbp+var_14]
0x180072324  mov     [rsp+80h+var_60], rax
0x180072329  call    ?GetProxyHostName@PROXY_SERVER_LIST@@QEAAHW4ProxyResolveScheme@@PEAW42@PEAPEAGPEAG@Z; PROXY_SERVER_LIST::GetProxyHostName(ProxyResolveScheme,ProxyResolveScheme *,ushort * *,ushort *)
0x18007232e  mov     r15d, eax
0x180072331  jmp     loc_180072242
0x180072336  mov     [rsp+80h+var_38], r13
0x18007233b  mov     [rsp+80h+var_40], rcx
0x180072340  mov     [rsp+80h+var_48], rax
0x180072345  mov     [rsp+80h+var_50], r9
0x18007234a  mov     r9, rsi
0x18007234d  mov     [rsp+80h+var_58], r14
0x180072352  mov     dword ptr [rsp+80h+var_60], ebx
0x180072356  call    WPP_SF_qDqqqqq
0x18007235b  jmp     loc_1800720E9
0x180072360  mov     r9, [r14+8]
0x180072364  lea     r8, WPP_bbb471cff1993fcc2367af86668fb1d1_Traceguids
0x18007236b  mov     edx, 11h
0x180072370  mov     ecx, 405h
0x180072375  call    WPP_SF_S
0x18007237a  jmp     loc_180072125
0x18007237f  mov     edx, 12h
0x180072384  lea     r8, WPP_bbb471cff1993fcc2367af86668fb1d1_Traceguids
0x18007238b  mov     ecx, 405h
0x180072390  call    WPP_SF_
0x180072395  jmp     loc_180072145
0x18007239a  mov     [rbp+var_2C], 29Fh
0x1800723a1  jmp     loc_18007225B
0x1800723a6  mov     [rbp+var_2C], 2AEh
0x1800723ad  jmp     loc_180072260
0x1800723b2  mov     edx, 13h
0x1800723b7  lea     r8, WPP_bbb471cff1993fcc2367af86668fb1d1_Traceguids
0x1800723be  mov     ecx, 405h
0x1800723c3  mov     r9d, ebx
0x1800723c6  call    WPP_SF_d
0x1800723cb  jmp     loc_1800721E8
```
