# ScWrapMoveClusterGroup(_HCLUSTER *,_HGROUP *,_HNODE *,ulong,long *,wchar_t const *)

- ea: `0x180098f5c`
- end: `0x18009914f`
- name: `?ScWrapMoveClusterGroup@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEAU_HNODE@@KPEAJPEB_W@Z`
- size: `499`
- prototype: `unsigned int(struct _HCLUSTER *, struct _HGROUP *, struct _HNODE *, unsigned int, int *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180036cf0`

## callees

- `0x180098ecc`
- `0x180098f5c`
- `0x180099158`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800990db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098faa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800990db`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009905f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18009905f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ff2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099073`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009909e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009910d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009911c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180098ff2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180099073`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009909e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009910d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009911c`
- `CLUSAPI!MoveClusterGroupEx2` at `0x180098fd6`
- `CLUSAPI!MoveClusterGroupEx2` at `0x180098fd6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009908a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18009908a`

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
0x180098f5c  mov     [rsp-28h+arg_8], rbx
0x180098f61  mov     [rsp-28h+arg_10], rsi
0x180098f66  mov     [rsp-28h+arg_0], rcx
0x180098f6b  push    rbp
0x180098f6c  push    rdi
0x180098f6d  push    r12
0x180098f6f  push    r14
0x180098f71  push    r15
0x180098f73  mov     rbp, rsp
0x180098f76  sub     rsp, 40h
0x180098f7a  mov     r14, rdx
0x180098f7d  mov     [rbp+hMem], 0
0x180098f85  xor     edi, edi
0x180098f87  lea     rdx, [rbp+hMem]; wchar_t **
0x180098f8b  xor     esi, esi
0x180098f8d  mov     dword ptr [rbp+arg_0], edi
0x180098f90  mov     rcx, r14; hGroup
0x180098f93  mov     [rbp+var_8], rsi
0x180098f97  mov     r15d, r9d
0x180098f9a  mov     rbx, r8
0x180098f9d  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x180098fa2  mov     r12d, eax
0x180098fa5  cmp     eax, 0FFFFFFFFh
0x180098fa8  jnz     short loc_180098FBD
0x180098faa  call    cs:__imp_GetLastError
0x180098fb1  nop     dword ptr [rax+rax+00h]
0x180098fb6  mov     ebx, eax
0x180098fb8  jmp     loc_180099109
0x180098fbd  mov     rax, [rbp+arg_28]
0x180098fc1  xor     r9d, r9d
0x180098fc4  mov     qword ptr [rsp+40h+cchCount2], rax
0x180098fc9  xor     r8d, r8d
0x180098fcc  mov     rdx, rbx
0x180098fcf  mov     dword ptr [rsp+40h+lpString2], esi
0x180098fd3  mov     rcx, r14
0x180098fd6  call    cs:__imp_MoveClusterGroupEx2
0x180098fdd  nop     dword ptr [rax+rax+00h]
0x180098fe2  mov     ebx, eax
0x180098fe4  test    r15d, r15d
0x180098fe7  jnz     short loc_18009900B
0x180098fe9  mov     rcx, [rbp+hMem]; hMem
0x180098fed  test    rcx, rcx
0x180098ff0  jz      short loc_180099002
0x180098ff2  call    cs:__imp_LocalFree
0x180098ff9  nop     dword ptr [rax+rax+00h]
0x180098ffe  mov     [rbp+hMem], rsi
0x180099002  lea     rdx, [rbp+hMem]
0x180099006  jmp     loc_1800990F1
0x18009900b  cmp     eax, 3E5h
0x180099010  jnz     loc_1800990EF
0x180099016  cmp     r15d, 0FFFFFFFFh
0x18009901a  mov     ebx, 12Ch
0x18009901f  cmovnz  ebx, r15d
0x180099023  mov     r15d, 1
0x180099029  lea     rdx, [rbp+var_8]; wchar_t **
0x18009902d  mov     rcx, r14; hGroup
0x180099030  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x180099035  cmp     eax, 0FFFFFFFFh
0x180099038  jz      loc_1800990DB
0x18009903e  mov     rsi, [rbp+var_8]
0x180099042  or      r9d, 0FFFFFFFFh; cchCount1
0x180099046  mov     r8, [rbp+hMem]; lpString1
0x18009904a  mov     edx, r15d; dwCmpFlags
0x18009904d  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x180099055  mov     ecx, 400h; Locale
0x18009905a  mov     [rsp+40h+lpString2], rsi; lpString2
0x18009905f  call    cs:__imp_CompareStringW
0x180099066  nop     dword ptr [rax+rax+00h]
0x18009906b  cmp     eax, 2
0x18009906e  jnz     short loc_18009909B
0x180099070  mov     rcx, rsi; hMem
0x180099073  call    cs:__imp_LocalFree
0x18009907a  nop     dword ptr [rax+rax+00h]
0x18009907f  xor     esi, esi
0x180099081  mov     ecx, 3E8h; dwMilliseconds
0x180099086  mov     [rbp+var_8], rsi
0x18009908a  call    cs:__imp_Sleep
0x180099091  nop     dword ptr [rax+rax+00h]
0x180099096  add     ebx, 0FFFFFFFFh
0x180099099  jnz     short loc_180099029
0x18009909b  mov     rcx, rsi; hMem
0x18009909e  call    cs:__imp_LocalFree
0x1800990a5  nop     dword ptr [rax+rax+00h]
0x1800990aa  xor     esi, esi
0x1800990ac  test    ebx, ebx
0x1800990ae  jnz     short loc_1800990BA
0x1800990b0  mov     edi, r15d
0x1800990b3  mov     ebx, 3E5h
0x1800990b8  jmp     short loc_180099109
0x1800990ba  lea     rax, [rbp+arg_0]
0x1800990be  mov     r9d, ebx
0x1800990c1  mov     r8d, r12d
0x1800990c4  mov     [rsp+40h+lpString2], rax; __int64
0x1800990c9  mov     edx, r12d
0x1800990cc  mov     rcx, r14; hGroup
0x1800990cf  call    ScWaitForGroupState
0x1800990d4  mov     edi, dword ptr [rbp+arg_0]
0x1800990d7  mov     ebx, eax
0x1800990d9  jmp     short loc_180099109
0x1800990db  call    cs:__imp_GetLastError
0x1800990e2  nop     dword ptr [rax+rax+00h]
0x1800990e7  mov     rsi, [rbp+var_8]
0x1800990eb  mov     ebx, eax
0x1800990ed  jmp     short loc_180099109
0x1800990ef  xor     edx, edx; wchar_t **
0x1800990f1  mov     rcx, r14; hGroup
0x1800990f4  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x1800990f9  cmp     eax, 0FFFFFFFFh
0x1800990fc  jz      loc_180098FAA
0x180099102  cmp     eax, 4
0x180099105  setz    dil
0x180099109  mov     rcx, [rbp+hMem]; hMem
0x18009910d  call    cs:__imp_LocalFree
0x180099114  nop     dword ptr [rax+rax+00h]
0x180099119  mov     rcx, rsi; hMem
0x18009911c  call    cs:__imp_LocalFree
0x180099123  nop     dword ptr [rax+rax+00h]
0x180099128  mov     rax, [rbp+arg_20]
0x18009912c  test    rax, rax
0x18009912f  jz      short loc_180099133
0x180099131  mov     [rax], edi
0x180099133  lea     r11, [rsp+40h+var_s0]
0x180099138  mov     eax, ebx
0x18009913a  mov     rbx, [r11+38h]
0x18009913e  mov     rsi, [r11+40h]
0x180099142  mov     rsp, r11
0x180099145  pop     r15
0x180099147  pop     r14
0x180099149  pop     r12
0x18009914b  pop     rdi
0x18009914c  pop     rbp
0x18009914d  retn
```
