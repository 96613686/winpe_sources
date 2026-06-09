# ScWrapMoveClusterGroup(_HCLUSTER *,_HGROUP *,_HNODE *,ulong,long *,wchar_t const *)

- ea: `0x180096da8`
- end: `0x180096f5e`
- name: `?ScWrapMoveClusterGroup@@YAKPEAU_HCLUSTER@@PEAU_HGROUP@@PEAU_HNODE@@KPEAJPEB_W@Z`
- size: `438`
- prototype: `unsigned int(struct _HCLUSTER *, struct _HGROUP *, struct _HNODE *, unsigned int, int *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180035b50`

## callees

- `0x180096d28`
- `0x180096da8`
- `0x180096f64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096efd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096efd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180096e99`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180096e99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096e32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096ea7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096ec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096f32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096e32`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096ea7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096ec6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096f29`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180096f32`
- `CLUSAPI!MoveClusterGroupEx2` at `0x180096e1c`
- `CLUSAPI!MoveClusterGroupEx2` at `0x180096e1c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180096eb8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180096eb8`

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
0x180096da8  mov     [rsp-28h+arg_8], rbx
0x180096dad  mov     [rsp-28h+arg_10], rsi
0x180096db2  mov     [rsp-28h+arg_0], rcx
0x180096db7  push    rbp
0x180096db8  push    rdi
0x180096db9  push    r12
0x180096dbb  push    r14
0x180096dbd  push    r15
0x180096dbf  mov     rbp, rsp
0x180096dc2  sub     rsp, 40h
0x180096dc6  mov     r14, rdx
0x180096dc9  mov     [rbp+hMem], 0
0x180096dd1  xor     edi, edi
0x180096dd3  lea     rdx, [rbp+hMem]; wchar_t **
0x180096dd7  xor     esi, esi
0x180096dd9  mov     dword ptr [rbp+arg_0], edi
0x180096ddc  mov     rcx, r14; hGroup
0x180096ddf  mov     [rbp+var_8], rsi
0x180096de3  mov     r15d, r9d
0x180096de6  mov     rbx, r8
0x180096de9  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x180096dee  mov     r12d, eax
0x180096df1  cmp     eax, 0FFFFFFFFh
0x180096df4  jnz     short loc_180096E03
0x180096df6  call    cs:__imp_GetLastError
0x180096dfc  mov     ebx, eax
0x180096dfe  jmp     loc_180096F25
0x180096e03  mov     rax, [rbp+arg_28]
0x180096e07  xor     r9d, r9d
0x180096e0a  mov     qword ptr [rsp+40h+cchCount2], rax
0x180096e0f  xor     r8d, r8d
0x180096e12  mov     rdx, rbx
0x180096e15  mov     dword ptr [rsp+40h+lpString2], esi
0x180096e19  mov     rcx, r14
0x180096e1c  call    cs:__imp_MoveClusterGroupEx2
0x180096e22  mov     ebx, eax
0x180096e24  test    r15d, r15d
0x180096e27  jnz     short loc_180096E45
0x180096e29  mov     rcx, [rbp+hMem]; hMem
0x180096e2d  test    rcx, rcx
0x180096e30  jz      short loc_180096E3C
0x180096e32  call    cs:__imp_LocalFree
0x180096e38  mov     [rbp+hMem], rsi
0x180096e3c  lea     rdx, [rbp+hMem]
0x180096e40  jmp     loc_180096F0D
0x180096e45  cmp     eax, 3E5h
0x180096e4a  jnz     loc_180096F0B
0x180096e50  cmp     r15d, 0FFFFFFFFh
0x180096e54  mov     ebx, 12Ch
0x180096e59  cmovnz  ebx, r15d
0x180096e5d  mov     r15d, 1
0x180096e63  lea     rdx, [rbp+var_8]; wchar_t **
0x180096e67  mov     rcx, r14; hGroup
0x180096e6a  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x180096e6f  cmp     eax, 0FFFFFFFFh
0x180096e72  jz      loc_180096EFD
0x180096e78  mov     rsi, [rbp+var_8]
0x180096e7c  or      r9d, 0FFFFFFFFh; cchCount1
0x180096e80  mov     r8, [rbp+hMem]; lpString1
0x180096e84  mov     edx, r15d; dwCmpFlags
0x180096e87  mov     [rsp+40h+cchCount2], 0FFFFFFFFh; cchCount2
0x180096e8f  mov     ecx, 400h; Locale
0x180096e94  mov     [rsp+40h+lpString2], rsi; lpString2
0x180096e99  call    cs:__imp_CompareStringW
0x180096e9f  cmp     eax, 2
0x180096ea2  jnz     short loc_180096EC3
0x180096ea4  mov     rcx, rsi; hMem
0x180096ea7  call    cs:__imp_LocalFree
0x180096ead  xor     esi, esi
0x180096eaf  mov     ecx, 3E8h; dwMilliseconds
0x180096eb4  mov     [rbp+var_8], rsi
0x180096eb8  call    cs:__imp_Sleep
0x180096ebe  add     ebx, 0FFFFFFFFh
0x180096ec1  jnz     short loc_180096E63
0x180096ec3  mov     rcx, rsi; hMem
0x180096ec6  call    cs:__imp_LocalFree
0x180096ecc  xor     esi, esi
0x180096ece  test    ebx, ebx
0x180096ed0  jnz     short loc_180096EDC
0x180096ed2  mov     edi, r15d
0x180096ed5  mov     ebx, 3E5h
0x180096eda  jmp     short loc_180096F25
0x180096edc  lea     rax, [rbp+arg_0]
0x180096ee0  mov     r9d, ebx
0x180096ee3  mov     r8d, r12d
0x180096ee6  mov     [rsp+40h+lpString2], rax; __int64
0x180096eeb  mov     edx, r12d
0x180096eee  mov     rcx, r14; hGroup
0x180096ef1  call    ScWaitForGroupState
0x180096ef6  mov     edi, dword ptr [rbp+arg_0]
0x180096ef9  mov     ebx, eax
0x180096efb  jmp     short loc_180096F25
0x180096efd  call    cs:__imp_GetLastError
0x180096f03  mov     rsi, [rbp+var_8]
0x180096f07  mov     ebx, eax
0x180096f09  jmp     short loc_180096F25
0x180096f0b  xor     edx, edx; wchar_t **
0x180096f0d  mov     rcx, r14; hGroup
0x180096f10  call    ?WrapGetClusterGroupState@@YA?AW4CLUSTER_GROUP_STATE@@PEAU_HGROUP@@PEAPEA_W@Z; WrapGetClusterGroupState(_HGROUP *,wchar_t * *)
0x180096f15  cmp     eax, 0FFFFFFFFh
0x180096f18  jz      loc_180096DF6
0x180096f1e  cmp     eax, 4
0x180096f21  setz    dil
0x180096f25  mov     rcx, [rbp+hMem]; hMem
0x180096f29  call    cs:__imp_LocalFree
0x180096f2f  mov     rcx, rsi; hMem
0x180096f32  call    cs:__imp_LocalFree
0x180096f38  mov     rax, [rbp+arg_20]
0x180096f3c  test    rax, rax
0x180096f3f  jz      short loc_180096F43
0x180096f41  mov     [rax], edi
0x180096f43  lea     r11, [rsp+40h+var_s0]
0x180096f48  mov     eax, ebx
0x180096f4a  mov     rbx, [r11+38h]
0x180096f4e  mov     rsi, [r11+40h]
0x180096f52  mov     rsp, r11
0x180096f55  pop     r15
0x180096f57  pop     r14
0x180096f59  pop     r12
0x180096f5b  pop     rdi
0x180096f5c  pop     rbp
0x180096f5d  retn
```
