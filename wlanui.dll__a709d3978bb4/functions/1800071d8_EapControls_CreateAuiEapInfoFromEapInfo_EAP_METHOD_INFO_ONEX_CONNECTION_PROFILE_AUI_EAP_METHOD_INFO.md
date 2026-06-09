# EapControls::CreateAuiEapInfoFromEapInfo(_EAP_METHOD_INFO *,_ONEX_CONNECTION_PROFILE *,_AUI_EAP_METHOD_INFO * *)

- ea: `0x1800071d8`
- end: `0x180007396`
- name: `?CreateAuiEapInfoFromEapInfo@EapControls@@QEAAKPEAU_EAP_METHOD_INFO@@PEAU_ONEX_CONNECTION_PROFILE@@PEAPEAU_AUI_EAP_METHOD_INFO@@@Z`
- size: `446`
- prototype: `unsigned int __fastcall(EapControls *__hidden this, struct _EAP_METHOD_INFO *, struct _ONEX_CONNECTION_PROFILE *, struct _AUI_EAP_METHOD_INFO **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008944`

## callees

- `0x180001e26`
- `0x1800071d8`
- `0x180015814`
- `0x18001bf0a`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000720b`
- `KERNEL32!HeapAlloc` at `0x180007242`
- `KERNEL32!HeapAlloc` at `0x180007287`
- `KERNEL32!HeapAlloc` at `0x1800072f9`
- `KERNEL32!HeapAlloc` at `0x18000720b`
- `KERNEL32!HeapAlloc` at `0x180007242`
- `KERNEL32!HeapAlloc` at `0x180007287`
- `KERNEL32!HeapAlloc` at `0x1800072f9`
- `KERNEL32!GetProcessHeap` at `0x1800071f8`
- `KERNEL32!GetProcessHeap` at `0x180007231`
- `KERNEL32!GetProcessHeap` at `0x180007276`
- `KERNEL32!GetProcessHeap` at `0x1800072e8`
- `KERNEL32!GetProcessHeap` at `0x180007332`
- `KERNEL32!GetProcessHeap` at `0x180007346`
- `KERNEL32!GetProcessHeap` at `0x18000735a`
- `KERNEL32!GetProcessHeap` at `0x1800071f8`
- `KERNEL32!GetProcessHeap` at `0x180007231`
- `KERNEL32!GetProcessHeap` at `0x180007276`
- `KERNEL32!GetProcessHeap` at `0x1800072e8`
- `KERNEL32!GetProcessHeap` at `0x180007332`
- `KERNEL32!GetProcessHeap` at `0x180007346`
- `KERNEL32!GetProcessHeap` at `0x18000735a`
- `KERNEL32!HeapFree` at `0x180007340`
- `KERNEL32!HeapFree` at `0x180007354`
- `KERNEL32!HeapFree` at `0x180007368`
- `KERNEL32!HeapFree` at `0x180007340`
- `KERNEL32!HeapFree` at `0x180007354`
- `KERNEL32!HeapFree` at `0x180007368`

## pseudocode

```c
__int64 __fastcall EapControls::CreateAuiEapInfoFromEapInfo(
        EapControls *this,
        struct _EAP_METHOD_INFO *a2,
        struct _ONEX_CONNECTION_PROFILE *a3,
        struct _AUI_EAP_METHOD_INFO **a4)
{
  void *v5; // r14
  HANDLE ProcessHeap; // rax
  _OWORD *v9; // rdi
  EAP_METHOD_TYPE *v10; // rsi
  HANDLE v11; // rax
  EAP_METHOD_TYPE *v12; // rax
  __int64 v13; // rax
  SIZE_T v14; // rbx
  HANDLE v15; // rax
  void *v16; // rax
  int v17; // eax
  unsigned int v18; // ebx
  HANDLE v19; // rax
  LPVOID v20; // rax
  unsigned int v21; // ebx
  HANDLE v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  _OWORD v26[5]; // [rsp+20h] [rbp-58h] BYREF

  v5 = 0;
  ProcessHeap = GetProcessHeap();
  v9 = HeapAlloc(ProcessHeap, 8u, 0x28u);
  if ( v9 )
  {
    *v9 = 0;
    v9[1] = 0;
    *((_QWORD *)v9 + 4) = 0;
    v11 = GetProcessHeap();
    v12 = (EAP_METHOD_TYPE *)HeapAlloc(v11, 8u, 0x10u);
    v10 = v12;
    if ( !v12 )
      goto LABEL_9;
    *v12 = a2->eaptype;
    v13 = -1;
    do
      ++v13;
    while ( a2->pwszFriendlyName[v13] );
    v14 = 2 * v13 + 2;
    v15 = GetProcessHeap();
    v16 = HeapAlloc(v15, 8u, v14);
    v5 = v16;
    if ( !v16 )
      goto LABEL_9;
    memset_0(v16, 0, v14);
    memcpy_0(v5, a2->pwszFriendlyName, v14);
    v26[0] = a2->eaptype;
    v17 = ((__int64 (__fastcall *)(struct _ONEX_CONNECTION_PROFILE *, _OWORD *, _QWORD, char *))OneXGetEapConnectionData)(
            a3,
            v26,
            0,
            (char *)v9 + 8);
    *((_QWORD *)v9 + 2) = 0;
    if ( v17 == 234 )
    {
      v18 = *((_DWORD *)v9 + 2);
      v19 = GetProcessHeap();
      v20 = HeapAlloc(v19, 8u, v18);
      *((_QWORD *)v9 + 2) = v20;
      if ( !v20 )
        goto LABEL_9;
      v26[0] = a2->eaptype;
      v21 = ((__int64 (__fastcall *)(struct _ONEX_CONNECTION_PROFILE *, _OWORD *, LPVOID, char *))OneXGetEapConnectionData)(
              a3,
              v26,
              v20,
              (char *)v9 + 8);
      if ( v21 )
        goto LABEL_11;
    }
    else
    {
      v21 = 0;
    }
    *(_QWORD *)v9 = v10;
    *((_QWORD *)v9 + 3) = v5;
    *((_DWORD *)v9 + 8) = a2->eapProperties;
    *a4 = (struct _AUI_EAP_METHOD_INFO *)v9;
    return v21;
  }
  v10 = 0;
LABEL_9:
  v21 = 14;
LABEL_11:
  v22 = GetProcessHeap();
  HeapFree(v22, 0, v10);
  v23 = GetProcessHeap();
  HeapFree(v23, 0, v5);
  v24 = GetProcessHeap();
  HeapFree(v24, 0, v9);
  return v21;
}

```

## disassembly

```asm
0x1800071d8  push    rbx
0x1800071da  push    rbp
0x1800071db  push    rsi
0x1800071dc  push    rdi
0x1800071dd  push    r12
0x1800071df  push    r13
0x1800071e1  push    r14
0x1800071e3  push    r15
0x1800071e5  sub     rsp, 38h
0x1800071e9  xor     r15d, r15d
0x1800071ec  mov     r13, r9
0x1800071ef  mov     r14d, r15d
0x1800071f2  mov     r12, r8
0x1800071f5  mov     rbp, rdx
0x1800071f8  call    cs:__imp_GetProcessHeap
0x1800071fe  lea     ebx, [r15+8]
0x180007202  mov     rcx, rax; hHeap
0x180007205  mov     edx, ebx; dwFlags
0x180007207  lea     r8d, [r15+28h]; dwBytes
0x18000720b  call    cs:__imp_HeapAlloc
0x180007211  mov     rdi, rax
0x180007214  test    rax, rax
0x180007217  jnz     short loc_180007221
0x180007219  mov     esi, r15d
0x18000721c  jmp     loc_180007308
0x180007221  xorps   xmm0, xmm0
0x180007224  xor     eax, eax
0x180007226  movups  xmmword ptr [rdi], xmm0
0x180007229  movups  xmmword ptr [rdi+10h], xmm0
0x18000722d  mov     [rdi+20h], rax
0x180007231  call    cs:__imp_GetProcessHeap
0x180007237  mov     r8d, 10h; dwBytes
0x18000723d  mov     edx, ebx; dwFlags
0x18000723f  mov     rcx, rax; hHeap
0x180007242  call    cs:__imp_HeapAlloc
0x180007248  mov     rsi, rax
0x18000724b  test    rax, rax
0x18000724e  jz      loc_180007308
0x180007254  movups  xmm0, xmmword ptr [rbp+0]
0x180007258  movdqu  xmmword ptr [rax], xmm0
0x18000725c  mov     rcx, [rbp+18h]
0x180007260  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007264  inc     rax
0x180007267  cmp     [rcx+rax*2], r15w
0x18000726c  jnz     short loc_180007264
0x18000726e  lea     rbx, ds:2[rax*2]
0x180007276  call    cs:__imp_GetProcessHeap
0x18000727c  mov     r8, rbx; dwBytes
0x18000727f  mov     edx, 8; dwFlags
0x180007284  mov     rcx, rax; hHeap
0x180007287  call    cs:__imp_HeapAlloc
0x18000728d  mov     r14, rax
0x180007290  test    rax, rax
0x180007293  jz      short loc_180007308
0x180007295  mov     r8, rbx; Size
0x180007298  xor     edx, edx; Val
0x18000729a  mov     rcx, rax; void *
0x18000729d  call    memset_0
0x1800072a2  mov     rdx, [rbp+18h]; Src
0x1800072a6  mov     r8, rbx; Size
0x1800072a9  mov     rcx, r14; void *
0x1800072ac  call    memcpy_0
0x1800072b1  movups  xmm0, xmmword ptr [rbp+0]
0x1800072b5  lea     r15, [rdi+8]
0x1800072b9  xor     r8d, r8d
0x1800072bc  mov     r9, r15
0x1800072bf  lea     rdx, [rsp+78h+var_58]
0x1800072c4  mov     rcx, r12
0x1800072c7  movdqu  [rsp+78h+var_58], xmm0
0x1800072cd  call    OneXGetEapConnectionData
0x1800072d2  mov     qword ptr [rdi+10h], 0
0x1800072da  cmp     eax, 0EAh
0x1800072df  jnz     loc_180007370
0x1800072e5  mov     ebx, [r15]
0x1800072e8  call    cs:__imp_GetProcessHeap
0x1800072ee  mov     r8d, ebx; dwBytes
0x1800072f1  mov     edx, 8; dwFlags
0x1800072f6  mov     rcx, rax; hHeap
0x1800072f9  call    cs:__imp_HeapAlloc
0x1800072ff  mov     [rdi+10h], rax
0x180007303  test    rax, rax
0x180007306  jnz     short loc_18000730F
0x180007308  mov     ebx, 0Eh
0x18000730d  jmp     short loc_180007332
0x18000730f  movups  xmm0, xmmword ptr [rbp+0]
0x180007313  mov     r9, r15
0x180007316  lea     rdx, [rsp+78h+var_58]
0x18000731b  mov     r8, rax
0x18000731e  mov     rcx, r12
0x180007321  movdqu  [rsp+78h+var_58], xmm0
0x180007327  call    OneXGetEapConnectionData
0x18000732c  mov     ebx, eax
0x18000732e  test    eax, eax
0x180007330  jz      short loc_180007372
0x180007332  call    cs:__imp_GetProcessHeap
0x180007338  mov     r8, rsi; lpMem
0x18000733b  xor     edx, edx; dwFlags
0x18000733d  mov     rcx, rax; hHeap
0x180007340  call    cs:__imp_HeapFree
0x180007346  call    cs:__imp_GetProcessHeap
0x18000734c  mov     r8, r14; lpMem
0x18000734f  xor     edx, edx; dwFlags
0x180007351  mov     rcx, rax; hHeap
0x180007354  call    cs:__imp_HeapFree
0x18000735a  call    cs:__imp_GetProcessHeap
0x180007360  mov     r8, rdi; lpMem
0x180007363  xor     edx, edx; dwFlags
0x180007365  mov     rcx, rax; hHeap
0x180007368  call    cs:__imp_HeapFree
0x18000736e  jmp     short loc_180007383
0x180007370  xor     ebx, ebx
0x180007372  mov     [rdi], rsi
0x180007375  mov     [rdi+18h], r14
0x180007379  mov     eax, [rbp+20h]
0x18000737c  mov     [rdi+20h], eax
0x18000737f  mov     [r13+0], rdi
0x180007383  mov     eax, ebx
0x180007385  add     rsp, 38h
0x180007389  pop     r15
0x18000738b  pop     r14
0x18000738d  pop     r13
0x18000738f  pop     r12
0x180007391  pop     rdi
0x180007392  pop     rsi
0x180007393  pop     rbp
0x180007394  pop     rbx
0x180007395  retn
```
