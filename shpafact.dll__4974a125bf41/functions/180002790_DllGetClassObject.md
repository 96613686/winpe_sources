# DllGetClassObject

- ea: `0x180002790`
- end: `0x1800028c4`
- name: `DllGetClassObject`
- size: `308`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800026d4`
- `0x180002790`
- `0x180004010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002805`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002805`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800027f3`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  HRESULT v6; // ebx
  HANDLE ProcessHeap; // rax
  char *v8; // rax
  char *v9; // rsi
  _QWORD *v10; // rcx

  *ppv = 0;
  if ( *(_OWORD *)riid == *(_OWORD *)&IID_IClassFactory
    || (v6 = -2147221231, *(_QWORD *)&riid->Data1 == *(_QWORD *)&IID_IUnknown.Data1)
    && *(_QWORD *)riid->Data4 == *(_QWORD *)IID_IUnknown.Data4 )
  {
    ProcessHeap = GetProcessHeap();
    v8 = (char *)HeapAlloc(ProcessHeap, 8u, 0x20u);
    v9 = v8;
    if ( v8 )
    {
      *(_QWORD *)v8 = &CClassFactory::`vftable';
      *(IID *)(v8 + 8) = *rclsid;
      _InterlockedIncrement(&g_cDllRefs);
      _InterlockedIncrement((volatile signed __int32 *)v8 + 6);
      v6 = (**(__int64 (__fastcall ***)(LPVOID, const IID *const, LPVOID *))v8)(v8, riid, ppv);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
      if ( v6 >= 0 )
        return v6;
    }
    else
    {
      v10 = WPP_GLOBAL_Control;
      v6 = -2147024882;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        return v6;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_11;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_8681af7930fc3f9ff14ce17035134427_Traceguids, 2147942414LL);
    }
  }
  v10 = WPP_GLOBAL_Control;
LABEL_11:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 4) != 0 )
    WPP_SF_d(v10[2], 11, &WPP_18a2193733963c00b13dba0ff53a5177_Traceguids, (unsigned int)v6);
  return v6;
}

```

## disassembly

```asm
0x180002790  push    rbx
0x180002792  push    rbp
0x180002793  push    rsi
0x180002794  push    rdi
0x180002795  push    r14
0x180002797  push    r15
0x180002799  sub     rsp, 28h
0x18000279d  mov     qword ptr [r8], 0
0x1800027a4  lea     r15, WPP_GLOBAL_Control
0x1800027ab  mov     rax, [rdx]
0x1800027ae  mov     r14, r8
0x1800027b1  cmp     rax, qword ptr cs:IID_IClassFactory.Data1
0x1800027b8  mov     rdi, rdx
0x1800027bb  mov     rbp, rcx
0x1800027be  jnz     short loc_1800027CD
0x1800027c0  mov     rax, [rdx+8]
0x1800027c4  cmp     rax, qword ptr cs:IID_IClassFactory.Data4
0x1800027cb  jz      short loc_1800027F3
0x1800027cd  mov     rax, [rdx]
0x1800027d0  mov     ebx, 80040111h
0x1800027d5  cmp     rax, qword ptr cs:IID_IUnknown.Data1
0x1800027dc  jnz     loc_18000288B
0x1800027e2  mov     rax, [rdx+8]
0x1800027e6  cmp     rax, qword ptr cs:IID_IUnknown.Data4
0x1800027ed  jnz     loc_18000288B
0x1800027f3  call    cs:__imp_GetProcessHeap
0x1800027f9  mov     edx, 8; dwFlags
0x1800027fe  mov     rcx, rax; hHeap
0x180002801  lea     r8d, [rdx+18h]; dwBytes
0x180002805  call    cs:__imp_HeapAlloc
0x18000280b  mov     rsi, rax
0x18000280e  test    rax, rax
0x180002811  jz      short loc_18000285C
0x180002813  lea     rax, ??_7CClassFactory@@6B@; const CClassFactory::`vftable'
0x18000281a  mov     [rsi], rax
0x18000281d  movups  xmm0, xmmword ptr [rbp+0]
0x180002821  movdqu  xmmword ptr [rsi+8], xmm0
0x180002826  lock inc cs:?g_cDllRefs@@3JA; long g_cDllRefs
0x18000282d  lock inc dword ptr [rsi+18h]
0x180002831  mov     rax, [rsi]
0x180002834  mov     r8, r14
0x180002837  mov     rdx, rdi
0x18000283a  mov     rcx, rsi
0x18000283d  mov     rax, [rax]
0x180002840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002845  mov     ebx, eax
0x180002847  mov     rcx, rsi
0x18000284a  mov     rax, [rsi]
0x18000284d  mov     rax, [rax+10h]
0x180002851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002856  test    ebx, ebx
0x180002858  jns     short loc_1800028B5
0x18000285a  jmp     short loc_18000288B
0x18000285c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002863  mov     ebx, 8007000Eh
0x180002868  cmp     rcx, r15
0x18000286b  jz      short loc_1800028B5
0x18000286d  test    byte ptr [rcx+1Ch], 4
0x180002871  jz      short loc_180002892
0x180002873  mov     rcx, [rcx+10h]
0x180002877  lea     r8, WPP_8681af7930fc3f9ff14ce17035134427_Traceguids
0x18000287e  mov     edx, 0Ah
0x180002883  mov     r9d, ebx
0x180002886  call    WPP_SF_d
0x18000288b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002892  cmp     rcx, r15
0x180002895  jz      short loc_1800028B5
0x180002897  test    byte ptr [rcx+1Ch], 4
0x18000289b  jz      short loc_1800028B5
0x18000289d  mov     rcx, [rcx+10h]
0x1800028a1  lea     r8, WPP_18a2193733963c00b13dba0ff53a5177_Traceguids
0x1800028a8  mov     edx, 0Bh
0x1800028ad  mov     r9d, ebx
0x1800028b0  call    WPP_SF_d
0x1800028b5  mov     eax, ebx
0x1800028b7  add     rsp, 28h
0x1800028bb  pop     r15
0x1800028bd  pop     r14
0x1800028bf  pop     rdi
0x1800028c0  pop     rsi
0x1800028c1  pop     rbp
0x1800028c2  pop     rbx
0x1800028c3  retn
```
