# ScWrapMoveClusterGroup(_HCLUSTER *,_HGROUP *,_HNODE *,ulong,long *,wchar_t const *)

- ea: `0x18003cc5c`
- end: `0x18003ce4f`
- name: `?ScWrapMoveClusterGroup@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEAU_HNODE@@KPEAJPEB_W@Z`
- size: `499`
- prototype: `unsigned int(struct _HCLUSTER *, struct _HGROUP *, struct _HNODE *, unsigned int, int *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180032eb0`

## callees

- `0x18003cbcc`
- `0x18003cc5c`
- `0x18003ce58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ccaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cddb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ccaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003cddb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003cd5f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18003cd5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ccf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cd73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cd9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ce0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ce1c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ccf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cd73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003cd9e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ce0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003ce1c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003cd8a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003cd8a`
- `CLUSAPI!MoveClusterGroupEx2` at `0x18003ccd6`
- `CLUSAPI!MoveClusterGroupEx2` at `0x18003ccd6`

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
0x18003cc5c  mov     [rsp-28h+arg_8], rbx
0x18003cc61  mov     [rsp-28h+arg_10], rsi
0x18003cc66  mov     [rsp-28h+arg_0], rcx
0x18003cc6b  push    rbp
0x18003cc6c  push    rdi
0x18003cc6d  push    r12
0x18003cc6f  push    r14
0x18003cc71  push    r15
0x18003cc73  mov     rbp, rsp
0x18003cc76  sub     rsp, 40h
0x18003cc7a  mov     r14, rdx
0x18003cc7d  mov     [rbp+hMem], 0
0x18003cc85  xor     edi, edi
0x18003cc87  lea     rdx, [rbp+hMem]; wchar_t **
0x18003cc8b  xor     esi, esi
0x18003cc8d  mov     dword ptr [rbp+arg_0], edi
0x18003cc90  mov     rcx, r14; hGroup
0x18003cc93  mov     [rbp+var_8], rsi
0x18003cc97  mov     r15d, r9d
0x18003cc9a  mov     rbx, r8
0x18003cc9d  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x18003cca2  mov     r12d, eax
0x18003cca5  cmp     eax, 0FFFFFFFFh
0x18003cca8  jnz     short loc_18003CCBD
0x18003ccaa  call    cs:__imp_GetLastError
0x18003ccb1  nop     dword ptr [rax+rax+00h]
0x18003ccb6  mov     ebx, eax
0x18003ccb8  jmp     loc_18003CE09
0x18003ccbd  mov     rax, [rbp+arg_28]
0x18003ccc1  xor     r9d, r9d
0x18003ccc4  mov     qword ptr [rsp+40h+cchCount2], rax
0x18003ccc9  xor     r8d, r8d
0x18003cccc  mov     rdx, rbx
0x18003cccf  mov     dword ptr [rsp+40h+lpString2], esi
0x18003ccd3  mov     rcx, r14
0x18003ccd6  call    cs:__imp_MoveClusterGroupEx2
0x18003ccdd  nop     dword ptr [rax+rax+00h]
0x18003cce2  mov     ebx, eax
0x18003cce4  test    r15d, r15d
0x18003cce7  jnz     short loc_18003CD0B
0x18003cce9  mov     rcx, [rbp+hMem]; hMem
0x18003cced  test    rcx, rcx
0x18003ccf0  jz      short loc_18003CD02
0x18003ccf2  call    cs:__imp_LocalFree
0x18003ccf9  nop     dword ptr [rax+rax+00h]
0x18003ccfe  mov     [rbp+hMem], rsi
0x18003cd02  lea     rdx, [rbp+hMem]
0x18003cd06  jmp     loc_18003CDF1
0x18003cd0b  cmp     eax, 3E5h
0x18003cd10  jnz     loc_18003CDEF
0x18003cd16  cmp     r15d, 0FFFFFFFFh
0x18003cd1a  mov     ebx, 12Ch
0x18003cd1f  cmovnz  ebx, r15d
0x18003cd23  mov     r15d, 1
0x18003cd29  lea     rdx, [rbp+var_8]; wchar_t **
0x18003cd2d  mov     rcx, r14; hGroup
0x18003cd30  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x18003cd35  cmp     eax, 0FFFFFFFFh
0x18003cd38  jz      loc_18003CDDB
0x18003cd3e  mov     rsi, [rbp+var_8]
0x18003cd42  or      r9d, 0FFFFFFFFh; cchCount1
0x18003cd46  mov     r8, [rbp+hMem]; lpString1
0x18003cd4a  mov     edx, r15d; dwCmpFlags
0x18003cd4d  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x18003cd55  mov     ecx, 400h; Locale
0x18003cd5a  mov     [rsp+40h+lpString2], rsi; lpString2
0x18003cd5f  call    cs:__imp_CompareStringW
0x18003cd66  nop     dword ptr [rax+rax+00h]
0x18003cd6b  cmp     eax, 2
0x18003cd6e  jnz     short loc_18003CD9B
0x18003cd70  mov     rcx, rsi; hMem
0x18003cd73  call    cs:__imp_LocalFree
0x18003cd7a  nop     dword ptr [rax+rax+00h]
0x18003cd7f  xor     esi, esi
0x18003cd81  mov     ecx, 3E8h; dwMilliseconds
0x18003cd86  mov     [rbp+var_8], rsi
0x18003cd8a  call    cs:__imp_Sleep
0x18003cd91  nop     dword ptr [rax+rax+00h]
0x18003cd96  add     ebx, 0FFFFFFFFh
0x18003cd99  jnz     short loc_18003CD29
0x18003cd9b  mov     rcx, rsi; hMem
0x18003cd9e  call    cs:__imp_LocalFree
0x18003cda5  nop     dword ptr [rax+rax+00h]
0x18003cdaa  xor     esi, esi
0x18003cdac  test    ebx, ebx
0x18003cdae  jnz     short loc_18003CDBA
0x18003cdb0  mov     edi, r15d
0x18003cdb3  mov     ebx, 3E5h
0x18003cdb8  jmp     short loc_18003CE09
0x18003cdba  lea     rax, [rbp+arg_0]
0x18003cdbe  mov     r9d, ebx
0x18003cdc1  mov     r8d, r12d
0x18003cdc4  mov     [rsp+40h+lpString2], rax; __int64
0x18003cdc9  mov     edx, r12d
0x18003cdcc  mov     rcx, r14; hGroup
0x18003cdcf  call    ScWaitForGroupState
0x18003cdd4  mov     edi, dword ptr [rbp+arg_0]
0x18003cdd7  mov     ebx, eax
0x18003cdd9  jmp     short loc_18003CE09
0x18003cddb  call    cs:__imp_GetLastError
0x18003cde2  nop     dword ptr [rax+rax+00h]
0x18003cde7  mov     rsi, [rbp+var_8]
0x18003cdeb  mov     ebx, eax
0x18003cded  jmp     short loc_18003CE09
0x18003cdef  xor     edx, edx; wchar_t **
0x18003cdf1  mov     rcx, r14; hGroup
0x18003cdf4  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x18003cdf9  cmp     eax, 0FFFFFFFFh
0x18003cdfc  jz      loc_18003CCAA
0x18003ce02  cmp     eax, 4
0x18003ce05  setz    dil
0x18003ce09  mov     rcx, [rbp+hMem]; hMem
0x18003ce0d  call    cs:__imp_LocalFree
0x18003ce14  nop     dword ptr [rax+rax+00h]
0x18003ce19  mov     rcx, rsi; hMem
0x18003ce1c  call    cs:__imp_LocalFree
0x18003ce23  nop     dword ptr [rax+rax+00h]
0x18003ce28  mov     rax, [rbp+arg_20]
0x18003ce2c  test    rax, rax
0x18003ce2f  jz      short loc_18003CE33
0x18003ce31  mov     [rax], edi
0x18003ce33  lea     r11, [rsp+40h+var_s0]
0x18003ce38  mov     eax, ebx
0x18003ce3a  mov     rbx, [r11+38h]
0x18003ce3e  mov     rsi, [r11+40h]
0x18003ce42  mov     rsp, r11
0x18003ce45  pop     r15
0x18003ce47  pop     r14
0x18003ce49  pop     r12
0x18003ce4b  pop     rdi
0x18003ce4c  pop     rbp
0x18003ce4d  retn
```
