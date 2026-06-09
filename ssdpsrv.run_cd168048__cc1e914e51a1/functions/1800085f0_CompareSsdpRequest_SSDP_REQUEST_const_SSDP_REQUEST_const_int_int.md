# CompareSsdpRequest(_SSDP_REQUEST const *,_SSDP_REQUEST const *,int *,int *)

- ea: `0x1800085f0`
- end: `0x1800087f7`
- name: `?CompareSsdpRequest@@YAHPEBU_SSDP_REQUEST@@0PEAH1@Z`
- size: `519`
- prototype: `__int64 __fastcall(const struct _SSDP_REQUEST *, const struct _SSDP_REQUEST *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006a60`

## callees

- `0x1800085f0`
- `0x1800271fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000862b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800087a9`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000862b`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800087a9`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000872c`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000874b`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180008769`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180008785`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000872c`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x18000874b`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180008769`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x180008785`

## pseudocode

```c
__int64 __fastcall CompareSsdpRequest(const struct _SSDP_REQUEST *a1, const struct _SSDP_REQUEST *a2, int *a3, int *a4)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  unsigned int v10; // ebp
  LPCSTR v11; // r10
  unsigned int i; // ebx
  __int64 v13; // r9
  __int64 v14; // r8
  unsigned __int8 *v15; // rax
  __int64 v16; // r8
  __int64 v17; // r8
  int v18; // ecx
  int v19; // edx
  __int64 v21; // r8
  unsigned __int8 *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25; // r9d
  int v26; // eax
  char *v27; // rax
  char *v28; // rdi
  char *v29; // rax

  v6 = *((_QWORD *)a2 + 10);
  v7 = *((_QWORD *)a1 + 10);
  *a3 = 0;
  v10 = 1;
  *a4 = 0;
  if ( (unsigned int)_o__stricmp(*(_QWORD *)(v7 + 48), *(_QWORD *)(v6 + 48)) )
  {
    v21 = *((_QWORD *)a1 + 10);
    v22 = *(unsigned __int8 **)(v21 + 152);
    if ( !v22 )
      goto LABEL_14;
    v23 = *(_QWORD *)(*((_QWORD *)a2 + 10) + 152LL);
    if ( !v23 )
      goto LABEL_14;
    v24 = v23 - (_QWORD)v22;
    do
    {
      v25 = v22[v24];
      v26 = *v22 - v25;
      if ( v26 )
        break;
      ++v22;
    }
    while ( v25 );
    if ( v26 )
      goto LABEL_14;
    v27 = strstr(*(const char **)(v21 + 48), "//");
    v28 = v27;
    if ( v27 )
      v28 = strstr(v27 + 2, "/");
    v29 = strstr(*(const char **)(*((_QWORD *)a2 + 10) + 48LL), "//");
    if ( v29 )
      v29 = strstr(v29 + 2, "/");
    if ( v28 && v29 && (unsigned int)_o__stricmp(v28, v29) )
    {
LABEL_14:
      *a3 = 1;
      v10 = 0;
    }
  }
  v11 = WPP_GLOBAL_Control;
  for ( i = 0; i < 3; ++i )
  {
    v13 = *(int *)&CompareHeaders[4 * i];
    v14 = 8 * v13;
    v15 = *(unsigned __int8 **)(8 * v13 + *((_QWORD *)a1 + 10));
    if ( v15 )
    {
      v16 = *(_QWORD *)(v14 + *((_QWORD *)a2 + 10));
      if ( !v16 )
        goto LABEL_11;
      v17 = v16 - (_QWORD)v15;
      do
      {
        v18 = v15[v17];
        v19 = *v15 - v18;
        if ( v19 )
          break;
        ++v15;
      }
      while ( v18 );
      if ( v19 )
      {
        if ( v11 != (LPCSTR)&WPP_GLOBAL_Control && (v11[28] & 0x10) != 0 )
        {
          WPP_SF_d(*((_QWORD *)v11 + 2), 67, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids, v13);
          v11 = WPP_GLOBAL_Control;
        }
LABEL_11:
        v10 = 0;
        *a4 = 1;
        continue;
      }
    }
    else if ( *(_QWORD *)(v14 + *((_QWORD *)a2 + 10)) )
    {
      v10 = 0;
      *a4 = 1;
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800085f0  push    rbx
0x1800085f2  push    rbp
0x1800085f3  push    rsi
0x1800085f4  push    rdi
0x1800085f5  push    r12
0x1800085f7  push    r13
0x1800085f9  push    r14
0x1800085fb  push    r15
0x1800085fd  sub     rsp, 28h
0x180008601  mov     r14, rdx
0x180008604  mov     rsi, rcx
0x180008607  mov     rdx, [rdx+50h]
0x18000860b  xor     r12d, r12d
0x18000860e  mov     rcx, [rcx+50h]
0x180008612  mov     r15, r9
0x180008615  mov     rbx, r8
0x180008618  mov     [r8], r12d
0x18000861b  mov     ebp, 1
0x180008620  mov     [r9], r12d
0x180008623  mov     rdx, [rdx+30h]
0x180008627  mov     rcx, [rcx+30h]
0x18000862b  call    cs:__imp__o__stricmp
0x180008632  nop     dword ptr [rax+rax+00h]
0x180008637  test    eax, eax
0x180008639  jnz     loc_1800086C5
0x18000863f  mov     r10, cs:WPP_GLOBAL_Control
0x180008646  lea     rdi, ?CompareHeaders@@3PAHA; "\b"
0x18000864d  mov     ebx, r12d
0x180008650  lea     r13, WPP_GLOBAL_Control
0x180008657  movsxd  rax, ebx
0x18000865a  movsxd  r9, dword ptr [rdi+rax*4]
0x18000865e  mov     rax, [rsi+50h]
0x180008662  lea     r8, ds:0[r9*8]
0x18000866a  mov     rax, [r8+rax]
0x18000866e  test    rax, rax
0x180008671  jz      short loc_1800086EF
0x180008673  mov     rcx, [r14+50h]
0x180008677  mov     r8, [r8+rcx]
0x18000867b  test    r8, r8
0x18000867e  jz      short loc_1800086B9
0x180008680  sub     r8, rax
0x180008683  movzx   edx, byte ptr [rax]
0x180008686  movzx   ecx, byte ptr [rax+r8]
0x18000868b  sub     edx, ecx
0x18000868d  jnz     short loc_180008696
0x18000868f  inc     rax
0x180008692  test    ecx, ecx
0x180008694  jnz     short loc_180008683
0x180008696  test    edx, edx
0x180008698  jnz     loc_1800087C2
0x18000869e  inc     ebx
0x1800086a0  cmp     ebx, 3
0x1800086a3  jb      short loc_180008657
0x1800086a5  mov     eax, ebp
0x1800086a7  add     rsp, 28h
0x1800086ab  pop     r15
0x1800086ad  pop     r14
0x1800086af  pop     r13
0x1800086b1  pop     r12
0x1800086b3  pop     rdi
0x1800086b4  pop     rsi
0x1800086b5  pop     rbp
0x1800086b6  pop     rbx
0x1800086b7  retn
0x1800086b9  mov     ebp, r12d
0x1800086bc  mov     dword ptr [r15], 1
0x1800086c3  jmp     short loc_18000869E
0x1800086c5  mov     r8, [rsi+50h]
0x1800086c9  mov     rcx, [r8+98h]
0x1800086d0  test    rcx, rcx
0x1800086d3  jz      short loc_1800086E5
0x1800086d5  mov     rax, [r14+50h]
0x1800086d9  mov     rdx, [rax+98h]
0x1800086e0  test    rdx, rdx
0x1800086e3  jnz     short loc_180008705
0x1800086e5  mov     [rbx], ebp
0x1800086e7  mov     ebp, r12d
0x1800086ea  jmp     loc_18000863F
0x1800086ef  mov     rax, [r14+50h]
0x1800086f3  cmp     [r8+rax], r12
0x1800086f7  jz      short loc_18000869E
0x1800086f9  mov     ebp, r12d
0x1800086fc  mov     dword ptr [r15], 1
0x180008703  jmp     short loc_18000869E
0x180008705  sub     rdx, rcx
0x180008708  movzx   eax, byte ptr [rcx]
0x18000870b  movzx   r9d, byte ptr [rcx+rdx]
0x180008710  sub     eax, r9d
0x180008713  jnz     short loc_18000871D
0x180008715  inc     rcx
0x180008718  test    r9d, r9d
0x18000871b  jnz     short loc_180008708
0x18000871d  test    eax, eax
0x18000871f  jnz     short loc_1800086E5
0x180008721  mov     rcx, [r8+30h]; Str
0x180008725  lea     rdx, SubStr; "//"
0x18000872c  call    cs:__imp_strstr
0x180008733  nop     dword ptr [rax+rax+00h]
0x180008738  mov     rdi, rax
0x18000873b  test    rax, rax
0x18000873e  jz      short loc_18000875A
0x180008740  lea     rcx, [rax+2]; Str
0x180008744  lea     rdx, asc_18003E2FC; "/"
0x18000874b  call    cs:__imp_strstr
0x180008752  nop     dword ptr [rax+rax+00h]
0x180008757  mov     rdi, rax
0x18000875a  mov     rcx, [r14+50h]
0x18000875e  lea     rdx, SubStr; "//"
0x180008765  mov     rcx, [rcx+30h]; Str
0x180008769  call    cs:__imp_strstr
0x180008770  nop     dword ptr [rax+rax+00h]
0x180008775  test    rax, rax
0x180008778  jz      short loc_180008791
0x18000877a  lea     rcx, [rax+2]; Str
0x18000877e  lea     rdx, asc_18003E2FC; "/"
0x180008785  call    cs:__imp_strstr
0x18000878c  nop     dword ptr [rax+rax+00h]
0x180008791  test    rdi, rdi
0x180008794  jz      loc_18000863F
0x18000879a  test    rax, rax
0x18000879d  jz      loc_18000863F
0x1800087a3  mov     rdx, rax
0x1800087a6  mov     rcx, rdi
0x1800087a9  call    cs:__imp__o__stricmp
0x1800087b0  nop     dword ptr [rax+rax+00h]
0x1800087b5  test    eax, eax
0x1800087b7  jz      loc_18000863F
0x1800087bd  jmp     loc_1800086E5
0x1800087c2  cmp     r10, r13
0x1800087c5  jz      loc_1800086B9
0x1800087cb  test    byte ptr [r10+1Ch], 10h
0x1800087d0  jz      loc_1800086B9
0x1800087d6  mov     rcx, [r10+10h]
0x1800087da  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x1800087e1  mov     edx, 43h ; 'C'
0x1800087e6  call    WPP_SF_d
0x1800087eb  mov     r10, cs:WPP_GLOBAL_Control
0x1800087f2  jmp     loc_1800086B9
```
