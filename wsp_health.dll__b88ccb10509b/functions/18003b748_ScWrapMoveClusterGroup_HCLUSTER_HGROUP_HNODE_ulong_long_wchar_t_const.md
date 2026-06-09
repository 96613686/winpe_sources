# ScWrapMoveClusterGroup(_HCLUSTER *,_HGROUP *,_HNODE *,ulong,long *,wchar_t const *)

- ea: `0x18003b748`
- end: `0x18003b8fe`
- name: `?ScWrapMoveClusterGroup@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEAU_HNODE@@KPEAJPEB_W@Z`
- size: `438`
- prototype: `unsigned int(struct _HCLUSTER *, struct _HGROUP *, struct _HNODE *, unsigned int, int *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180031e20`

## callees

- `0x18003b6c8`
- `0x18003b748`
- `0x18003b904`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b89d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b796`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b89d`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003b839`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003b839`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b847`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b7d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b847`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b866`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8c9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003b8d2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003b858`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003b858`
- `CLUSAPI!MoveClusterGroupEx2` at `0x18003b7bc`
- `CLUSAPI!MoveClusterGroupEx2` at `0x18003b7bc`

## pseudocode

```c
__int64 __fastcall ScWrapMoveClusterGroup(
        struct _HCLUSTER *a1,
        struct _HGROUP *a2,
        struct _HNODE *a3,
        int a4,
        int *a5,
        const wchar_t *a6)
{
  int v7; // edi
  WCHAR *v8; // rsi
  DWORD v11; // ebx
  DWORD v12; // eax
  wchar_t **p_hMem; // rdx
  int v14; // ebx
  WCHAR *v15; // rsi
  DWORD v16; // eax
  DWORD LastError; // eax
  enum CLUSTER_GROUP_STATE ClusterGroupState; // eax
  HLOCAL hMem; // [rsp+30h] [rbp-10h] BYREF
  PCNZWCH lpString2; // [rsp+38h] [rbp-8h] BYREF
  int v22; // [rsp+70h] [rbp+30h] BYREF
  int v23; // [rsp+74h] [rbp+34h]

  v23 = HIDWORD(a1);
  hMem = 0;
  v7 = 0;
  v8 = 0;
  v22 = 0;
  lpString2 = 0;
  if ( WrapGetClusterGroupState(a2, (wchar_t **)&hMem) == ClusterGroupStateUnknown )
    goto LABEL_2;
  v12 = MoveClusterGroupEx2(a2, a3, 0, 0, 0, a6);
  v11 = v12;
  if ( a4 )
  {
    if ( v12 == 997 )
    {
      v14 = 300;
      if ( a4 != -1 )
        v14 = a4;
      do
      {
        if ( WrapGetClusterGroupState(a2, (wchar_t **)&lpString2) == ClusterGroupStateUnknown )
        {
          LastError = GetLastError();
          v8 = (WCHAR *)lpString2;
          v11 = LastError;
          goto LABEL_20;
        }
        v15 = (WCHAR *)lpString2;
        if ( CompareStringW(0x400u, 1u, (PCNZWCH)hMem, -1, lpString2, -1) != 2 )
          break;
        LocalFree(v15);
        v15 = 0;
        lpString2 = 0;
        Sleep(0x3E8u);
        --v14;
      }
      while ( v14 );
      LocalFree(v15);
      v8 = 0;
      if ( v14 )
      {
        v16 = ScWaitForGroupState(a2, (__int64)&v22);
        v7 = v22;
        v11 = v16;
      }
      else
      {
        v7 = 1;
        v11 = 997;
      }
      goto LABEL_20;
    }
    p_hMem = 0;
  }
  else
  {
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    p_hMem = (wchar_t **)&hMem;
  }
  ClusterGroupState = WrapGetClusterGroupState(a2, p_hMem);
  if ( ClusterGroupState == ClusterGroupStateUnknown )
  {
LABEL_2:
    v11 = GetLastError();
    goto LABEL_20;
  }
  LOBYTE(v7) = ClusterGroupState == ClusterGroupPending;
LABEL_20:
  LocalFree(hMem);
  LocalFree(v8);
  if ( a5 )
    *a5 = v7;
  return v11;
}

```

## disassembly

```asm
0x18003b748  mov     [rsp-28h+arg_8], rbx
0x18003b74d  mov     [rsp-28h+arg_10], rsi
0x18003b752  mov     [rsp-28h+arg_0], rcx
0x18003b757  push    rbp
0x18003b758  push    rdi
0x18003b759  push    r12
0x18003b75b  push    r14
0x18003b75d  push    r15
0x18003b75f  mov     rbp, rsp
0x18003b762  sub     rsp, 40h
0x18003b766  mov     r14, rdx
0x18003b769  mov     [rbp+hMem], 0
0x18003b771  xor     edi, edi
0x18003b773  lea     rdx, [rbp+hMem]; wchar_t **
0x18003b777  xor     esi, esi
0x18003b779  mov     dword ptr [rbp+arg_0], edi
0x18003b77c  mov     rcx, r14; hGroup
0x18003b77f  mov     [rbp+var_8], rsi
0x18003b783  mov     r15d, r9d
0x18003b786  mov     rbx, r8
0x18003b789  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x18003b78e  mov     r12d, eax
0x18003b791  cmp     eax, 0FFFFFFFFh
0x18003b794  jnz     short loc_18003B7A3
0x18003b796  call    cs:__imp_GetLastError
0x18003b79c  mov     ebx, eax
0x18003b79e  jmp     loc_18003B8C5
0x18003b7a3  mov     rax, [rbp+arg_28]
0x18003b7a7  xor     r9d, r9d
0x18003b7aa  mov     qword ptr [rsp+40h+cchCount2], rax
0x18003b7af  xor     r8d, r8d
0x18003b7b2  mov     rdx, rbx
0x18003b7b5  mov     dword ptr [rsp+40h+lpString2], esi
0x18003b7b9  mov     rcx, r14
0x18003b7bc  call    cs:__imp_MoveClusterGroupEx2
0x18003b7c2  mov     ebx, eax
0x18003b7c4  test    r15d, r15d
0x18003b7c7  jnz     short loc_18003B7E5
0x18003b7c9  mov     rcx, [rbp+hMem]; hMem
0x18003b7cd  test    rcx, rcx
0x18003b7d0  jz      short loc_18003B7DC
0x18003b7d2  call    cs:__imp_LocalFree
0x18003b7d8  mov     [rbp+hMem], rsi
0x18003b7dc  lea     rdx, [rbp+hMem]
0x18003b7e0  jmp     loc_18003B8AD
0x18003b7e5  cmp     eax, 3E5h
0x18003b7ea  jnz     loc_18003B8AB
0x18003b7f0  cmp     r15d, 0FFFFFFFFh
0x18003b7f4  mov     ebx, 12Ch
0x18003b7f9  cmovnz  ebx, r15d
0x18003b7fd  mov     r15d, 1
0x18003b803  lea     rdx, [rbp+var_8]; wchar_t **
0x18003b807  mov     rcx, r14; hGroup
0x18003b80a  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x18003b80f  cmp     eax, 0FFFFFFFFh
0x18003b812  jz      loc_18003B89D
0x18003b818  mov     rsi, [rbp+var_8]
0x18003b81c  or      r9d, 0FFFFFFFFh; cchCount1
0x18003b820  mov     r8, [rbp+hMem]; lpString1
0x18003b824  mov     edx, r15d; dwCmpFlags
0x18003b827  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x18003b82f  mov     ecx, 400h; Locale
0x18003b834  mov     [rsp+40h+lpString2], rsi; lpString2
0x18003b839  call    cs:__imp_CompareStringW
0x18003b83f  cmp     eax, 2
0x18003b842  jnz     short loc_18003B863
0x18003b844  mov     rcx, rsi; hMem
0x18003b847  call    cs:__imp_LocalFree
0x18003b84d  xor     esi, esi
0x18003b84f  mov     ecx, 3E8h; dwMilliseconds
0x18003b854  mov     [rbp+var_8], rsi
0x18003b858  call    cs:__imp_Sleep
0x18003b85e  add     ebx, 0FFFFFFFFh
0x18003b861  jnz     short loc_18003B803
0x18003b863  mov     rcx, rsi; hMem
0x18003b866  call    cs:__imp_LocalFree
0x18003b86c  xor     esi, esi
0x18003b86e  test    ebx, ebx
0x18003b870  jnz     short loc_18003B87C
0x18003b872  mov     edi, r15d
0x18003b875  mov     ebx, 3E5h
0x18003b87a  jmp     short loc_18003B8C5
0x18003b87c  lea     rax, [rbp+arg_0]
0x18003b880  mov     r9d, ebx
0x18003b883  mov     r8d, r12d
0x18003b886  mov     [rsp+40h+lpString2], rax; __int64
0x18003b88b  mov     edx, r12d
0x18003b88e  mov     rcx, r14; hGroup
0x18003b891  call    ScWaitForGroupState
0x18003b896  mov     edi, dword ptr [rbp+arg_0]
0x18003b899  mov     ebx, eax
0x18003b89b  jmp     short loc_18003B8C5
0x18003b89d  call    cs:__imp_GetLastError
0x18003b8a3  mov     rsi, [rbp+var_8]
0x18003b8a7  mov     ebx, eax
0x18003b8a9  jmp     short loc_18003B8C5
0x18003b8ab  xor     edx, edx; wchar_t **
0x18003b8ad  mov     rcx, r14; hGroup
0x18003b8b0  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x18003b8b5  cmp     eax, 0FFFFFFFFh
0x18003b8b8  jz      loc_18003B796
0x18003b8be  cmp     eax, 4
0x18003b8c1  setz    dil
0x18003b8c5  mov     rcx, [rbp+hMem]; hMem
0x18003b8c9  call    cs:__imp_LocalFree
0x18003b8cf  mov     rcx, rsi; hMem
0x18003b8d2  call    cs:__imp_LocalFree
0x18003b8d8  mov     rax, [rbp+arg_20]
0x18003b8dc  test    rax, rax
0x18003b8df  jz      short loc_18003B8E3
0x18003b8e1  mov     [rax], edi
0x18003b8e3  lea     r11, [rsp+40h+var_s0]
0x18003b8e8  mov     eax, ebx
0x18003b8ea  mov     rbx, [r11+38h]
0x18003b8ee  mov     rsi, [r11+40h]
0x18003b8f2  mov     rsp, r11
0x18003b8f5  pop     r15
0x18003b8f7  pop     r14
0x18003b8f9  pop     r12
0x18003b8fb  pop     rdi
0x18003b8fc  pop     rbp
0x18003b8fd  retn
```
