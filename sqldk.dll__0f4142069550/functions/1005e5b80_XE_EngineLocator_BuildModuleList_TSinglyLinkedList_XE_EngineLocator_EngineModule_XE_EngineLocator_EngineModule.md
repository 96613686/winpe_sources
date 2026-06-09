# XE_EngineLocator::BuildModuleList(TSinglyLinkedList<XE_EngineLocator::EngineModule> *,XE_EngineLocator::EngineModule *,XEEngineAPISet const * const)

- ea: `0x1005e5b80`
- end: `0x1005e62b3`
- name: `?BuildModuleList@XE_EngineLocator@@CAHPEAV?$TSinglyLinkedList@UEngineModule@XE_EngineLocator@@@@PEAUEngineModule@1@QEBUXEEngineAPISet@@@Z`
- size: `1843`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x1005e62c0`

## callees

- `0x100403070`
- `0x100561190`
- `0x1005ba1a0`
- `0x1005e5b80`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1005e5f3d`
- `KERNEL32!HeapAlloc` at `0x1005e5f3d`
- `KERNEL32!GetProcessHeap` at `0x1005e5f2e`
- `KERNEL32!GetProcessHeap` at `0x1005e5f2e`
- `KERNEL32!Module32NextW` at `0x1005e5cd0`
- `KERNEL32!Module32NextW` at `0x1005e615e`
- `KERNEL32!Module32NextW` at `0x1005e5cd0`
- `KERNEL32!Module32NextW` at `0x1005e615e`
- `KERNEL32!GetProcAddress` at `0x1005e5e1d`
- `KERNEL32!GetProcAddress` at `0x1005e5e1d`
- `KERNEL32!CloseHandle` at `0x1005e61f5`
- `KERNEL32!CloseHandle` at `0x1005e61f5`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1005e5c77`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1005e5cb3`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1005e5c77`
- `KERNEL32!CreateToolhelp32Snapshot` at `0x1005e5cb3`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1005e5d18`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1005e5d2f`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1005e5d18`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1005e5d2f`

## string_xrefs

- `0x1005e5d28`: `.dll.patch`

## pseudocode

```c
__int64 __fastcall XE_EngineLocator::BuildModuleList(__int64 **a1, __m128i *a2, __int64 a3)
{
  unsigned int v6; // r15d
  int v7; // ebx
  __int64 v8; // rcx
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 *v11; // rax
  __int64 v12; // rcx
  HANDLE i; // rdi
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  const wchar_t *v18; // rbx
  HMODULE hModule; // rbx
  __int64 v21; // rcx
  __int64 *v22; // rax
  __int64 v23; // rcx
  __int64 *v24; // rax
  __int64 v25; // rcx
  FARPROC ProcAddress; // rax
  unsigned int v27; // edx
  __m128i v28; // xmm2
  __m128i v29; // xmm3
  __m128i v30; // xmm1
  __m128i v31; // xmm0
  __m128i v32; // xmm0
  _QWORD *v33; // rdx
  _QWORD *v34; // rdx
  _QWORD *v35; // rdx
  HANDLE ProcessHeap; // rax
  __m128i *v37; // rax
  __int64 *v38; // r8
  _QWORD *v39; // rdx
  _QWORD *v40; // rdx
  _QWORD *v41; // rdx
  __int64 *v42; // rcx
  unsigned __int64 v43; // rdx
  __int64 *v44; // rax
  __int16 *v45; // rcx
  __m128i v47; // [rsp+28h] [rbp-E0h]
  __m128i v48; // [rsp+38h] [rbp-D0h] BYREF
  __m128i v49; // [rsp+48h] [rbp-C0h]
  __m128i v50; // [rsp+58h] [rbp-B0h]
  __m128i v51; // [rsp+68h] [rbp-A0h] BYREF
  __m128i v52; // [rsp+78h] [rbp-90h] BYREF
  __int64 v53; // [rsp+88h] [rbp-80h]
  __int128 v54; // [rsp+98h] [rbp-70h]
  __m128i v55; // [rsp+A8h] [rbp-60h]
  __m128i v56; // [rsp+B8h] [rbp-50h]
  __m128i v57; // [rsp+C8h] [rbp-40h]
  __m128i v58; // [rsp+D8h] [rbp-30h] BYREF
  __m128i v59; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v60; // [rsp+F8h] [rbp-10h]
  MODULEENTRY32W me; // [rsp+108h] [rbp+0h] BYREF
  __int16 v62; // [rsp+548h] [rbp+440h] BYREF
  __int128 v63; // [rsp+54Ch] [rbp+444h]
  int v64; // [rsp+55Ch] [rbp+454h]
  __int16 v65; // [rsp+560h] [rbp+458h]
  int v66; // [rsp+568h] [rbp+460h]
  __int64 v67; // [rsp+570h] [rbp+468h]
  int v68; // [rsp+578h] [rbp+470h]
  MODULEENTRY32W *v69; // [rsp+580h] [rbp+478h]
  __int16 v70; // [rsp+5C8h] [rbp+4C0h] BYREF
  __int128 v71; // [rsp+5CCh] [rbp+4C4h]
  int v72; // [rsp+5DCh] [rbp+4D4h]
  __int16 v73; // [rsp+5E0h] [rbp+4D8h]
  int v74; // [rsp+5E8h] [rbp+4E0h]
  __int64 v75; // [rsp+5F0h] [rbp+4E8h]
  int v76; // [rsp+5F8h] [rbp+4F0h]
  MODULEENTRY32W *p_me; // [rsp+600h] [rbp+4F8h]
  __int16 v78[2]; // [rsp+648h] [rbp+540h] BYREF
  __int128 v79; // [rsp+64Ch] [rbp+544h]
  int v80; // [rsp+65Ch] [rbp+554h]
  __int16 v81; // [rsp+660h] [rbp+558h]
  int v82; // [rsp+668h] [rbp+560h]
  __int64 v83; // [rsp+670h] [rbp+568h]
  int v84; // [rsp+678h] [rbp+570h]
  MODULEENTRY32W *v85; // [rsp+680h] [rbp+578h]
  __int16 v86[2]; // [rsp+6C8h] [rbp+5C0h] BYREF
  __int128 v87; // [rsp+6CCh] [rbp+5C4h]
  int v88; // [rsp+6DCh] [rbp+5D4h]
  __int16 v89; // [rsp+6E0h] [rbp+5D8h]
  int v90; // [rsp+6E8h] [rbp+5E0h]
  __int64 v91; // [rsp+6F0h] [rbp+5E8h]

  v6 = 1;
  XEPackage0::Log_xe_engine_build_module_list(0, 0, a3);
  if ( !a1 )
    goto LABEL_44;
  LODWORD(v53) = 0;
  v49.m128i_i64[0] = (__int64)&v51.m128i_i64[1];
  v50.m128i_i64[0] = (__int64)&v52;
  v51.m128i_i64[0] = (__int64)&v52.m128i_i64[1];
  v7 = 0;
  v48.m128i_i32[0] = *(_DWORD *)a3;
  v8 = **(_QWORD **)(a3 + 16);
  v48.m128i_i16[4] = *(_WORD *)(a3 + 8);
  v9 = *(__int64 **)(a3 + 32);
  v51.m128i_i64[1] = v8;
  v10 = *v9;
  v49.m128i_i16[4] = *(_WORD *)(a3 + 24);
  v11 = *(__int64 **)(a3 + 48);
  v52.m128i_i64[0] = v10;
  v12 = *v11;
  v50.m128i_i16[4] = *(_WORD *)(a3 + 40);
  v48.m128i_i16[2] = *(_WORD *)(a3 + 4);
  LOWORD(v11) = *(_WORD *)(a3 + 6);
  v52.m128i_i64[1] = v12;
  v48.m128i_i16[3] = (__int16)v11;
  for ( i = CreateToolhelp32Snapshot(8u, 0); i == (HANDLE)-1LL; i = CreateToolhelp32Snapshot(8u, 0) )
  {
    v15 = v7++;
    if ( v15 >= 60 )
    {
      v6 = 0;
      XEPackage0::Log_xe_engine_build_module_list((XEPackage0 *)1, 0, v14);
      goto LABEL_44;
    }
    SOSHost::TaskSleep(XE_Engine::sm_pHost, 0x3E8u);
  }
  me.dwSize = 1080;
  if ( !Module32NextW(i, &me) )
    goto LABEL_43;
  while ( 1 )
  {
    v16 = -1;
    do
      ++v16;
    while ( me.szModule[v16] );
    v17 = v16 - 10;
    if ( v17 > 0 )
    {
      _mm_lfence();
      v18 = &me.szModule[v17];
      if ( !_wcsicmp(L".exe.patch", v18) || (_mm_lfence(), !_wcsicmp(L".dll.patch", v18)) )
      {
        v73 = 2;
        p_me = &me;
        v70 = 0;
        v71 = XEPackage0_GUID;
        v72 = 1879052288;
        v74 = 1610616832;
        v75 = 4;
        v76 = 1610616832;
        if ( !qword_100715148 || !qword_100714EC8 || !qword_100720EC8 )
          goto LABEL_37;
        v45 = &v70;
LABEL_36:
        qword_100715030(v45);
        goto LABEL_37;
      }
    }
    hModule = me.hModule;
    v56.m128i_i64[0] = (__int64)&v58.m128i_i64[1];
    LODWORD(v60) = 0;
    v54 = 0;
    v57.m128i_i64[0] = (__int64)&v59;
    v58.m128i_i64[0] = (__int64)&v59.m128i_i64[1];
    v55.m128i_i32[0] = *(_DWORD *)a3;
    v21 = **(_QWORD **)(a3 + 16);
    v55.m128i_i16[4] = *(_WORD *)(a3 + 8);
    v22 = *(__int64 **)(a3 + 32);
    v58.m128i_i64[1] = v21;
    v23 = *v22;
    v56.m128i_i16[4] = *(_WORD *)(a3 + 24);
    v24 = *(__int64 **)(a3 + 48);
    v59.m128i_i64[0] = v23;
    v25 = *v24;
    v57.m128i_i16[4] = *(_WORD *)(a3 + 40);
    v47.m128i_i64[0] = 0;
    v55.m128i_i16[2] = *(_WORD *)(a3 + 4);
    LOWORD(v24) = *(_WORD *)(a3 + 6);
    v49 = v56;
    v59.m128i_i64[1] = v25;
    v55.m128i_i16[3] = (__int16)v24;
    v51 = v58;
    v48 = v55;
    v53 = v60;
    v50 = v57;
    v52 = v59;
    ProcAddress = GetProcAddress(me.hModule, "XEGetEngine");
    if ( !ProcAddress || ((unsigned int (__fastcall *)(__m128i *, __int64))ProcAddress)(&v48, 1) )
    {
      LODWORD(v53) = 0;
      v63 = XEPackage0_GUID;
      v62 = 0;
      v64 = 1879052288;
      v65 = 2;
      v66 = 1610616832;
      v67 = 2;
      v68 = 1610616832;
      v69 = &me;
      if ( !qword_100715148 || !qword_100714EC8 || !qword_100720EC8 )
        goto LABEL_37;
      v45 = &v62;
      goto LABEL_36;
    }
    v47.m128i_i64[1] = (__int64)hModule;
    v27 = v50.m128i_u16[4] + v49.m128i_u16[4] + v48.m128i_u16[4] + v48.m128i_u16[3] + v48.m128i_u16[2];
    LODWORD(v53) = v27;
    if ( a2[6].m128i_i32[0] < v27 )
      break;
    if ( a2[6].m128i_i32[0] <= v27 )
      goto LABEL_20;
LABEL_37:
    if ( !Module32NextW(i, &me) )
      goto LABEL_43;
  }
  v28 = v48;
  v29 = v49;
  v30 = v51;
  *a2 = v47;
  v31 = v50;
  a2[1] = v28;
  a2[2] = v29;
  a2[3] = v31;
  v32 = v52;
  a2[4] = v30;
  v30.m128i_i64[0] = v53;
  a2[5] = v32;
  a2[6].m128i_i64[0] = v30.m128i_i64[0];
  a2[2].m128i_i64[0] = (__int64)&a2[4].m128i_i64[1];
  v33 = (_QWORD *)a2[2].m128i_i64[0];
  a2[3].m128i_i64[0] = (__int64)a2[5].m128i_i64;
  a2[4].m128i_i64[0] = (__int64)&a2[5].m128i_i64[1];
  a2[1].m128i_i32[0] = _mm_cvtsi128_si32(v28);
  *v33 = *(_QWORD *)v29.m128i_i64[0];
  v34 = (_QWORD *)a2[3].m128i_i64[0];
  a2[1].m128i_i16[4] = v48.m128i_i16[4];
  *v34 = *(_QWORD *)v50.m128i_i64[0];
  v35 = (_QWORD *)a2[4].m128i_i64[0];
  a2[2].m128i_i16[4] = v49.m128i_i16[4];
  *v35 = *(_QWORD *)v51.m128i_i64[0];
  a2[3].m128i_i16[4] = v50.m128i_i16[4];
  a2[1].m128i_i32[1] = v48.m128i_i32[1];
LABEL_20:
  ProcessHeap = GetProcessHeap();
  v37 = (__m128i *)HeapAlloc(ProcessHeap, 0, 0x68u);
  v38 = (__int64 *)v37;
  if ( v37 )
  {
    *v37 = v47;
    v37[1] = v48;
    v37[2] = v49;
    v37[3] = v50;
    v37[4] = v51;
    v37[5] = v52;
    v37[6].m128i_i64[0] = v53;
    v37[2].m128i_i64[0] = (__int64)&v37[4].m128i_i64[1];
    v39 = (_QWORD *)v37[2].m128i_i64[0];
    v37[3].m128i_i64[0] = (__int64)v37[5].m128i_i64;
    v37[4].m128i_i64[0] = (__int64)&v37[5].m128i_i64[1];
    v37[1].m128i_i32[0] = v48.m128i_i32[0];
    *v39 = *(_QWORD *)v49.m128i_i64[0];
    v40 = (_QWORD *)v37[3].m128i_i64[0];
    v37[1].m128i_i16[4] = v48.m128i_i16[4];
    *v40 = *(_QWORD *)v50.m128i_i64[0];
    v41 = (_QWORD *)v37[4].m128i_i64[0];
    v37[2].m128i_i16[4] = v49.m128i_i16[4];
    *v41 = *(_QWORD *)v51.m128i_i64[0];
    v37[3].m128i_i16[4] = v50.m128i_i16[4];
    v37[1].m128i_i32[1] = v48.m128i_i32[1];
    v42 = *a1;
    if ( *a1 && (v43 = v37->m128i_u64[1], v43 >= v42[1]) )
    {
      v44 = *a1;
      do
      {
        if ( v43 < v44[1] )
          break;
        v42 = v44;
        v44 = (__int64 *)*v44;
      }
      while ( v44 );
      *v38 = *v42;
      *v42 = (__int64)v38;
    }
    else
    {
      v37->m128i_i64[0] = (__int64)v42;
      *a1 = (__int64 *)v37;
    }
    goto LABEL_37;
  }
  v81 = 2;
  v6 = 0;
  v78[0] = 0;
  v85 = &me;
  v79 = XEPackage0_GUID;
  v80 = 1879052288;
  v82 = 1610616832;
  v83 = 3;
  v84 = 1610616832;
  if ( qword_100715148 && qword_100714EC8 && qword_100720EC8 )
    qword_100715030(v78);
LABEL_43:
  CloseHandle(i);
LABEL_44:
  v86[0] = 0;
  v87 = XEPackage0_GUID;
  v88 = 1879053312;
  v89 = 1;
  v90 = 1610616832;
  v91 = v6;
  if ( qword_100715148 && qword_100714EC8 && qword_100720EC8 )
    qword_100715030(v86);
  return v6;
}

```

## disassembly

```asm
0x1005e5b80  mov     r11, rsp
0x1005e5b83  push    rbp
0x1005e5b84  push    r15
0x1005e5b86  lea     rbp, [r11-688h]
0x1005e5b8d  sub     rsp, 778h
0x1005e5b94  mov     rax, cs:__security_cookie
0x1005e5b9b  xor     rax, rsp
0x1005e5b9e  mov     [rbp+680h+var_40], rax
0x1005e5ba5  mov     [r11-18h], rsi
0x1005e5ba9  mov     rsi, rdx
0x1005e5bac  mov     [r11-28h], r12
0x1005e5bb0  xor     edx, edx; __int64
0x1005e5bb2  mov     [r11-30h], r13
0x1005e5bb6  mov     r12, rcx
0x1005e5bb9  mov     [r11-38h], r14
0x1005e5bbd  xor     ecx, ecx; this
0x1005e5bbf  mov     r14, r8
0x1005e5bc2  lea     r15d, [rdx+1]
0x1005e5bc6  call    ?Log_xe_engine_build_module_list@XEPackage0@@YAX_J0@Z; XEPackage0::Log_xe_engine_build_module_list(__int64,__int64)
0x1005e5bcb  xor     r13d, r13d
0x1005e5bce  test    r12, r12
0x1005e5bd1  jz      loc_1005E620B
0x1005e5bd7  mov     dword ptr [rbp+680h+var_700], r13d
0x1005e5bdb  lea     rax, [rsp+780h+var_718]
0x1005e5be0  mov     qword ptr [rsp+780h+var_748+8], rax
0x1005e5be5  xorps   xmm0, xmm0
0x1005e5be8  movdqa  [rsp+780h+var_768+8], xmm0
0x1005e5bee  lea     rax, [rsp+780h+var_718+8]
0x1005e5bf3  mov     qword ptr [rsp+780h+var_738+8], rax
0x1005e5bf8  xor     edx, edx; th32ProcessID
0x1005e5bfa  lea     rax, [rsp+780h+var_718+10h]
0x1005e5bff  mov     [rsp+780h+arg_10], rbx
0x1005e5c07  mov     qword ptr [rsp+780h+var_728+8], rax
0x1005e5c0c  mov     ebx, r13d
0x1005e5c0f  mov     eax, [r14]
0x1005e5c12  mov     dword ptr [rsp+780h+var_758+8], eax
0x1005e5c16  mov     rax, [r14+10h]
0x1005e5c1a  mov     [rsp+780h+var_18], rdi
0x1005e5c22  mov     rcx, [rax]
0x1005e5c25  movzx   eax, word ptr [r14+8]
0x1005e5c2a  mov     word ptr [rsp+780h+var_748], ax
0x1005e5c2f  mov     rax, [r14+20h]
0x1005e5c33  mov     qword ptr [rsp+780h+var_718], rcx
0x1005e5c38  mov     rcx, [rax]
0x1005e5c3b  movzx   eax, word ptr [r14+18h]
0x1005e5c40  mov     word ptr [rsp+780h+var_738], ax
0x1005e5c45  mov     rax, [r14+30h]
0x1005e5c49  mov     qword ptr [rsp+780h+var_718+8], rcx
0x1005e5c4e  mov     rcx, [rax]
0x1005e5c51  movzx   eax, word ptr [r14+28h]
0x1005e5c56  mov     word ptr [rsp+780h+var_728], ax
0x1005e5c5b  movzx   eax, word ptr [r14+4]
0x1005e5c60  mov     word ptr [rsp+780h+var_758+0Ch], ax
0x1005e5c65  movzx   eax, word ptr [r14+6]
0x1005e5c6a  mov     qword ptr [rsp+780h+var_718+10h], rcx
0x1005e5c6f  lea     ecx, [rdx+8]; dwFlags
0x1005e5c72  mov     word ptr [rsp+780h+var_758+0Eh], ax
0x1005e5c77  call    cs:__imp_CreateToolhelp32Snapshot
0x1005e5c7d  mov     rdi, rax
0x1005e5c80  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1005e5c84  jnz     short loc_1005E5CC2
0x1005e5c86  nop     word ptr [rax+rax]
0x1005e5c8b  nop     dword ptr [rax+rax+00h]
0x1005e5c90  mov     eax, ebx
0x1005e5c92  inc     ebx
0x1005e5c94  cmp     eax, 3Ch ; '<'
0x1005e5c97  jge     loc_1005E5D3E
0x1005e5c9d  mov     rcx, cs:?sm_pHost@XE_Engine@@0PEAVSOSHost@@EA; this
0x1005e5ca4  mov     edx, 3E8h; unsigned int
0x1005e5ca9  call    ?TaskSleep@SOSHost@@QEAAJK@Z; SOSHost::TaskSleep(ulong)
0x1005e5cae  xor     edx, edx; th32ProcessID
0x1005e5cb0  lea     ecx, [rdx+8]; dwFlags
0x1005e5cb3  call    cs:__imp_CreateToolhelp32Snapshot
0x1005e5cb9  mov     rdi, rax
0x1005e5cbc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1005e5cc0  jz      short loc_1005E5C90
0x1005e5cc2  lea     rdx, [rbp+680h+me]; lpme
0x1005e5cc6  mov     [rbp+680h+me.dwSize], 438h
0x1005e5ccd  mov     rcx, rdi; hSnapshot
0x1005e5cd0  call    cs:__imp_Module32NextW
0x1005e5cd6  test    eax, eax
0x1005e5cd8  jz      loc_1005E61F2
0x1005e5cde  nop
0x1005e5cdf  nop
0x1005e5ce0  lea     rcx, [rbp+680h+me.szModule]
0x1005e5ce4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1005e5ceb  nop     dword ptr [rax+rax+00h]
0x1005e5cf0  inc     rax
0x1005e5cf3  cmp     [rcx+rax*2], r13w
0x1005e5cf8  jnz     short loc_1005E5CF0
0x1005e5cfa  sub     eax, 0Ah
0x1005e5cfd  test    eax, eax
0x1005e5cff  jle     short loc_1005E5D50
0x1005e5d01  lfence
0x1005e5d04  cdqe
0x1005e5d06  lea     rbx, [rbp+680h+me.szModule]
0x1005e5d0a  lea     rcx, aExePatch; ".exe.patch"
0x1005e5d11  lea     rbx, [rbx+rax*2]
0x1005e5d15  mov     rdx, rbx; String2
0x1005e5d18  call    cs:__imp__wcsicmp
0x1005e5d1e  test    eax, eax
0x1005e5d20  jz      short loc_1005E5D39
0x1005e5d22  lfence
0x1005e5d25  mov     rdx, rbx; String2
0x1005e5d28  lea     rcx, aDllPatch; ".dll.patch"
0x1005e5d2f  call    cs:__imp__wcsicmp
0x1005e5d35  test    eax, eax
0x1005e5d37  jnz     short loc_1005E5D50
0x1005e5d39  mov     eax, r15d
0x1005e5d3c  jmp     short loc_1005E5D53
0x1005e5d3e  xor     edx, edx; __int64
0x1005e5d40  mov     r15d, r13d
0x1005e5d43  lea     ecx, [rdx+1]; this
0x1005e5d46  call    ?Log_xe_engine_build_module_list@XEPackage0@@YAX_J0@Z; XEPackage0::Log_xe_engine_build_module_list(__int64,__int64)
0x1005e5d4b  jmp     loc_1005E61FB
0x1005e5d50  mov     eax, r13d
0x1005e5d53  test    eax, eax
0x1005e5d55  jnz     loc_1005E60D9
0x1005e5d5b  mov     rbx, [rbp+680h+me.hModule]
0x1005e5d5f  lea     rax, [rbp+680h+var_6B0+8]
0x1005e5d63  mov     qword ptr [rbp+680h+var_6D0], rax
0x1005e5d67  lea     rdx, ProcName; "XEGetEngine"
0x1005e5d6e  xorps   xmm0, xmm0
0x1005e5d71  mov     dword ptr [rbp+680h+var_690], r13d
0x1005e5d75  movdqu  [rbp+680h+var_6F0], xmm0
0x1005e5d7a  lea     rax, [rbp+680h+var_6A0]
0x1005e5d7e  mov     qword ptr [rbp+680h+var_6C0], rax
0x1005e5d82  lea     rax, [rbp+680h+var_6A0+8]
0x1005e5d86  mov     qword ptr [rbp+680h+var_6B0], rax
0x1005e5d8a  mov     eax, [r14]
0x1005e5d8d  mov     dword ptr [rbp+680h+var_6E0], eax
0x1005e5d90  mov     rax, [r14+10h]
0x1005e5d94  mov     rcx, [rax]
0x1005e5d97  movzx   eax, word ptr [r14+8]
0x1005e5d9c  mov     word ptr [rbp+680h+var_6E0+8], ax
0x1005e5da0  mov     rax, [r14+20h]
0x1005e5da4  mov     qword ptr [rbp+680h+var_6B0+8], rcx
0x1005e5da8  mov     rcx, [rax]
0x1005e5dab  movzx   eax, word ptr [r14+18h]
0x1005e5db0  mov     word ptr [rbp+680h+var_6D0+8], ax
0x1005e5db4  mov     rax, [r14+30h]
0x1005e5db8  movups  xmm1, [rbp+680h+var_6D0]
0x1005e5dbc  mov     qword ptr [rbp+680h+var_6A0], rcx
0x1005e5dc0  mov     rcx, [rax]
0x1005e5dc3  movzx   eax, word ptr [r14+28h]
0x1005e5dc8  mov     word ptr [rbp+680h+var_6C0+8], ax
0x1005e5dcc  movzx   eax, word ptr [r14+4]
0x1005e5dd1  movaps  [rsp+780h+var_768+8], xmm0
0x1005e5dd6  mov     word ptr [rbp+680h+var_6E0+4], ax
0x1005e5dda  movzx   eax, word ptr [r14+6]
0x1005e5ddf  movaps  [rsp+780h+var_748+8], xmm1
0x1005e5de4  movups  xmm1, [rbp+680h+var_6B0]
0x1005e5de8  mov     qword ptr [rbp+680h+var_6A0+8], rcx
0x1005e5dec  mov     rcx, rbx; hModule
0x1005e5def  mov     word ptr [rbp+680h+var_6E0+6], ax
0x1005e5df3  movups  xmm0, [rbp+680h+var_6E0]
0x1005e5df7  movaps  [rsp+780h+var_728+8], xmm1
0x1005e5dfc  movsd   xmm1, [rbp+680h+var_690]
0x1005e5e01  movaps  [rsp+780h+var_758+8], xmm0
0x1005e5e06  movups  xmm0, [rbp+680h+var_6C0]
0x1005e5e0a  movsd   [rbp+680h+var_700], xmm1
0x1005e5e0f  movaps  [rsp+780h+var_738+8], xmm0
0x1005e5e14  movups  xmm0, [rbp+680h+var_6A0]
0x1005e5e18  movaps  xmmword ptr [rsp+780h+var_718+8], xmm0
0x1005e5e1d  call    cs:__imp_GetProcAddress
0x1005e5e23  test    rax, rax
0x1005e5e26  jz      loc_1005E604E
0x1005e5e2c  mov     edx, r15d
0x1005e5e2f  lea     rcx, [rsp+780h+var_758+8]
0x1005e5e34  call    rax
0x1005e5e36  test    eax, eax
0x1005e5e38  jnz     loc_1005E604E
0x1005e5e3e  movzx   eax, word ptr [rsp+780h+var_758+0Eh]
0x1005e5e43  movzx   edx, word ptr [rsp+780h+var_758+0Ch]
0x1005e5e48  add     edx, eax
0x1005e5e4a  mov     qword ptr [rsp+780h+var_758], rbx
0x1005e5e4f  movzx   eax, word ptr [rsp+780h+var_748]
0x1005e5e54  add     edx, eax
0x1005e5e56  movzx   eax, word ptr [rsp+780h+var_738]
0x1005e5e5b  add     edx, eax
0x1005e5e5d  movzx   eax, word ptr [rsp+780h+var_728]
0x1005e5e62  add     edx, eax
0x1005e5e64  mov     dword ptr [rbp+680h+var_700], edx
0x1005e5e67  cmp     [rsi+60h], edx
0x1005e5e6a  jnb     loc_1005E5F28
0x1005e5e70  movaps  xmm0, [rsp+780h+var_768+8]
0x1005e5e75  lea     rax, [rsi+48h]
0x1005e5e79  movaps  xmm2, [rsp+780h+var_758+8]
0x1005e5e7e  movaps  xmm3, [rsp+780h+var_748+8]
0x1005e5e83  movaps  xmm1, [rsp+780h+var_728+8]
0x1005e5e88  movups  xmmword ptr [rsi], xmm0
0x1005e5e8b  movaps  xmm0, [rsp+780h+var_738+8]
0x1005e5e90  movups  xmmword ptr [rsi+10h], xmm2
0x1005e5e94  movups  xmmword ptr [rsi+20h], xmm3
0x1005e5e98  movups  xmmword ptr [rsi+30h], xmm0
0x1005e5e9c  movaps  xmm0, xmmword ptr [rsp+780h+var_718+8]
0x1005e5ea1  movups  xmmword ptr [rsi+40h], xmm1
0x1005e5ea5  movsd   xmm1, [rbp+680h+var_700]
0x1005e5eaa  movups  xmmword ptr [rsi+50h], xmm0
0x1005e5eae  movsd   qword ptr [rsi+60h], xmm1
0x1005e5eb3  mov     [rsi+20h], rax
0x1005e5eb7  lea     rax, [rsi+50h]
0x1005e5ebb  mov     rdx, [rsi+20h]
0x1005e5ebf  mov     [rsi+30h], rax
0x1005e5ec3  lea     rax, [rsi+58h]
0x1005e5ec7  mov     [rsi+40h], rax
0x1005e5ecb  movq    rax, xmm3
0x1005e5ed0  movd    dword ptr [rsi+10h], xmm2
0x1005e5ed5  mov     rcx, [rax]
0x1005e5ed8  mov     [rdx], rcx
0x1005e5edb  movzx   eax, word ptr [rsp+780h+var_748]
0x1005e5ee0  mov     rdx, [rsi+30h]
0x1005e5ee4  mov     [rsi+18h], ax
0x1005e5ee8  mov     rax, qword ptr [rsp+780h+var_738+8]
0x1005e5eed  mov     rcx, [rax]
0x1005e5ef0  mov     [rdx], rcx
0x1005e5ef3  movzx   eax, word ptr [rsp+780h+var_738]
0x1005e5ef8  mov     rdx, [rsi+40h]
0x1005e5efc  mov     [rsi+28h], ax
0x1005e5f00  mov     rax, qword ptr [rsp+780h+var_728+8]
0x1005e5f05  mov     rcx, [rax]
0x1005e5f08  mov     [rdx], rcx
0x1005e5f0b  movzx   eax, word ptr [rsp+780h+var_728]
0x1005e5f10  mov     [rsi+38h], ax
0x1005e5f14  movzx   eax, word ptr [rsp+780h+var_758+0Ch]
0x1005e5f19  mov     [rsi+14h], ax
0x1005e5f1d  movzx   eax, word ptr [rsp+780h+var_758+0Eh]
0x1005e5f22  mov     [rsi+16h], ax
0x1005e5f26  jmp     short loc_1005E5F2E
0x1005e5f28  ja      loc_1005E6157
0x1005e5f2e  call    cs:__imp_GetProcessHeap
0x1005e5f34  xor     edx, edx; dwFlags
0x1005e5f36  mov     rcx, rax; hHeap
0x1005e5f39  lea     r8d, [rdx+68h]; dwBytes
0x1005e5f3d  call    cs:__imp_HeapAlloc
0x1005e5f43  mov     r8, rax
0x1005e5f46  test    rax, rax
0x1005e5f49  jz      loc_1005E6171
0x1005e5f4f  movaps  xmm0, [rsp+780h+var_768+8]
0x1005e5f54  movups  xmmword ptr [rax], xmm0
0x1005e5f57  movaps  xmm1, [rsp+780h+var_758+8]
0x1005e5f5c  movups  xmmword ptr [rax+10h], xmm1
0x1005e5f60  movaps  xmm0, [rsp+780h+var_748+8]
0x1005e5f65  movups  xmmword ptr [rax+20h], xmm0
0x1005e5f69  movaps  xmm1, [rsp+780h+var_738+8]
0x1005e5f6e  movups  xmmword ptr [rax+30h], xmm1
0x1005e5f72  movaps  xmm0, [rsp+780h+var_728+8]
0x1005e5f77  movups  xmmword ptr [rax+40h], xmm0
0x1005e5f7b  movaps  xmm1, xmmword ptr [rsp+780h+var_718+8]
0x1005e5f80  movups  xmmword ptr [rax+50h], xmm1
0x1005e5f84  movsd   xmm0, [rbp+680h+var_700]
0x1005e5f89  movsd   qword ptr [rax+60h], xmm0
0x1005e5f8e  add     rax, 48h ; 'H'
0x1005e5f92  mov     [r8+20h], rax
0x1005e5f96  lea     rax, [r8+50h]
0x1005e5f9a  mov     rdx, [r8+20h]
0x1005e5f9e  mov     [r8+30h], rax
0x1005e5fa2  lea     rax, [r8+58h]
0x1005e5fa6  mov     [r8+40h], rax
0x1005e5faa  mov     eax, dword ptr [rsp+780h+var_758+8]
0x1005e5fae  mov     [r8+10h], eax
0x1005e5fb2  mov     rax, qword ptr [rsp+780h+var_748+8]
0x1005e5fb7  mov     rcx, [rax]
0x1005e5fba  mov     [rdx], rcx
0x1005e5fbd  movzx   eax, word ptr [rsp+780h+var_748]
0x1005e5fc2  mov     rdx, [r8+30h]
0x1005e5fc6  mov     [r8+18h], ax
0x1005e5fcb  mov     rax, qword ptr [rsp+780h+var_738+8]
0x1005e5fd0  mov     rcx, [rax]
0x1005e5fd3  mov     [rdx], rcx
0x1005e5fd6  movzx   eax, word ptr [rsp+780h+var_738]
0x1005e5fdb  mov     rdx, [r8+40h]
0x1005e5fdf  mov     [r8+28h], ax
0x1005e5fe4  mov     rax, qword ptr [rsp+780h+var_728+8]
0x1005e5fe9  mov     rcx, [rax]
0x1005e5fec  mov     [rdx], rcx
0x1005e5fef  movzx   eax, word ptr [rsp+780h+var_728]
0x1005e5ff4  mov     [r8+38h], ax
0x1005e5ff9  movzx   eax, word ptr [rsp+780h+var_758+0Ch]
0x1005e5ffe  mov     [r8+14h], ax
0x1005e6003  movzx   eax, word ptr [rsp+780h+var_758+0Eh]
0x1005e6008  mov     [r8+16h], ax
0x1005e600d  mov     rcx, [r12]
0x1005e6011  test    rcx, rcx
0x1005e6014  jz      short loc_1005E6042
0x1005e6016  mov     rdx, [r8+8]
0x1005e601a  cmp     rdx, [rcx+8]
0x1005e601e  jb      short loc_1005E6042
0x1005e6020  mov     rax, rcx
0x1005e6023  cmp     rdx, [rax+8]
0x1005e6027  jb      short loc_1005E6034
0x1005e6029  mov     rcx, rax
0x1005e602c  mov     rax, [rax]
0x1005e602f  test    rax, rax
0x1005e6032  jnz     short loc_1005E6023
0x1005e6034  mov     rax, [rcx]
0x1005e6037  mov     [r8], rax
0x1005e603a  mov     [rcx], r8
0x1005e603d  jmp     loc_1005E6157
0x1005e6042  mov     [r8], rcx
  ... truncated ...
```
