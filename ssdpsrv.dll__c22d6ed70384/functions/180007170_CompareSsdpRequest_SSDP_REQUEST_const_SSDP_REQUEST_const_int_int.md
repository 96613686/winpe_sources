# CompareSsdpRequest(_SSDP_REQUEST const *,_SSDP_REQUEST const *,int *,int *)

- ea: `0x180007170`
- end: `0x180007355`
- name: `?CompareSsdpRequest@@YAHPEBU_SSDP_REQUEST@@0PEAH1@Z`
- size: `485`
- prototype: `__int64 __fastcall(const struct _SSDP_REQUEST *, const struct _SSDP_REQUEST *, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005740`

## callees

- `0x180007170`
- `0x1800255a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800071ab`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000730d`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800071ab`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18000730d`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800072a8`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800072c1`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800072d9`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800072ef`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800072a8`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800072c1`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800072d9`
- `api-ms-win-crt-private-l1-1-0!strstr` at `0x1800072ef`

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
0x180007170  push    rbx
0x180007172  push    rbp
0x180007173  push    rsi
0x180007174  push    rdi
0x180007175  push    r12
0x180007177  push    r13
0x180007179  push    r14
0x18000717b  push    r15
0x18000717d  sub     rsp, 28h
0x180007181  mov     r14, rdx
0x180007184  mov     rsi, rcx
0x180007187  mov     rdx, [rdx+50h]
0x18000718b  xor     r12d, r12d
0x18000718e  mov     rcx, [rcx+50h]
0x180007192  mov     r15, r9
0x180007195  mov     rbx, r8
0x180007198  mov     [r8], r12d
0x18000719b  mov     ebp, 1
0x1800071a0  mov     [r9], r12d
0x1800071a3  mov     rdx, [rdx+30h]
0x1800071a7  mov     rcx, [rcx+30h]
0x1800071ab  call    cs:__imp__o__stricmp
0x1800071b1  test    eax, eax
0x1800071b3  jnz     loc_180007241
0x1800071b9  mov     r10, cs:WPP_GLOBAL_Control
0x1800071c0  lea     rdi, ?CompareHeaders@@3PAHA; "\b"
0x1800071c7  mov     ebx, r12d
0x1800071ca  lea     r13, WPP_GLOBAL_Control
0x1800071d1  movsxd  rax, ebx
0x1800071d4  movsxd  r9, dword ptr [rdi+rax*4]
0x1800071d8  mov     rax, [rsi+50h]
0x1800071dc  lea     r8, ds:0[r9*8]
0x1800071e4  mov     rax, [r8+rax]
0x1800071e8  test    rax, rax
0x1800071eb  jz      short loc_18000726B
0x1800071ed  mov     rcx, [r14+50h]
0x1800071f1  mov     r8, [r8+rcx]
0x1800071f5  test    r8, r8
0x1800071f8  jz      short loc_180007235
0x1800071fa  sub     r8, rax
0x1800071fd  nop     dword ptr [rax]
0x180007200  movzx   edx, byte ptr [rax]
0x180007203  movzx   ecx, byte ptr [rax+r8]
0x180007208  sub     edx, ecx
0x18000720a  jnz     short loc_180007213
0x18000720c  inc     rax
0x18000720f  test    ecx, ecx
0x180007211  jnz     short loc_180007200
0x180007213  test    edx, edx
0x180007215  jnz     loc_180007320
0x18000721b  inc     ebx
0x18000721d  cmp     ebx, 3
0x180007220  jb      short loc_1800071D1
0x180007222  mov     eax, ebp
0x180007224  add     rsp, 28h
0x180007228  pop     r15
0x18000722a  pop     r14
0x18000722c  pop     r13
0x18000722e  pop     r12
0x180007230  pop     rdi
0x180007231  pop     rsi
0x180007232  pop     rbp
0x180007233  pop     rbx
0x180007234  retn
0x180007235  mov     ebp, r12d
0x180007238  mov     dword ptr [r15], 1
0x18000723f  jmp     short loc_18000721B
0x180007241  mov     r8, [rsi+50h]
0x180007245  mov     rcx, [r8+98h]
0x18000724c  test    rcx, rcx
0x18000724f  jz      short loc_180007261
0x180007251  mov     rax, [r14+50h]
0x180007255  mov     rdx, [rax+98h]
0x18000725c  test    rdx, rdx
0x18000725f  jnz     short loc_180007281
0x180007261  mov     [rbx], ebp
0x180007263  mov     ebp, r12d
0x180007266  jmp     loc_1800071B9
0x18000726b  mov     rax, [r14+50h]
0x18000726f  cmp     [r8+rax], r12
0x180007273  jz      short loc_18000721B
0x180007275  mov     ebp, r12d
0x180007278  mov     dword ptr [r15], 1
0x18000727f  jmp     short loc_18000721B
0x180007281  sub     rdx, rcx
0x180007284  movzx   eax, byte ptr [rcx]
0x180007287  movzx   r9d, byte ptr [rcx+rdx]
0x18000728c  sub     eax, r9d
0x18000728f  jnz     short loc_180007299
0x180007291  inc     rcx
0x180007294  test    r9d, r9d
0x180007297  jnz     short loc_180007284
0x180007299  test    eax, eax
0x18000729b  jnz     short loc_180007261
0x18000729d  mov     rcx, [r8+30h]; Str
0x1800072a1  lea     rdx, SubStr; "//"
0x1800072a8  call    cs:__imp_strstr
0x1800072ae  mov     rdi, rax
0x1800072b1  test    rax, rax
0x1800072b4  jz      short loc_1800072CA
0x1800072b6  lea     rcx, [rax+2]; Str
0x1800072ba  lea     rdx, asc_18003B2EC; "/"
0x1800072c1  call    cs:__imp_strstr
0x1800072c7  mov     rdi, rax
0x1800072ca  mov     rcx, [r14+50h]
0x1800072ce  lea     rdx, SubStr; "//"
0x1800072d5  mov     rcx, [rcx+30h]; Str
0x1800072d9  call    cs:__imp_strstr
0x1800072df  test    rax, rax
0x1800072e2  jz      short loc_1800072F5
0x1800072e4  lea     rcx, [rax+2]; Str
0x1800072e8  lea     rdx, asc_18003B2EC; "/"
0x1800072ef  call    cs:__imp_strstr
0x1800072f5  test    rdi, rdi
0x1800072f8  jz      loc_1800071B9
0x1800072fe  test    rax, rax
0x180007301  jz      loc_1800071B9
0x180007307  mov     rdx, rax
0x18000730a  mov     rcx, rdi
0x18000730d  call    cs:__imp__o__stricmp
0x180007313  test    eax, eax
0x180007315  jz      loc_1800071B9
0x18000731b  jmp     loc_180007261
0x180007320  cmp     r10, r13
0x180007323  jz      loc_180007235
0x180007329  test    byte ptr [r10+1Ch], 10h
0x18000732e  jz      loc_180007235
0x180007334  mov     rcx, [r10+10h]
0x180007338  lea     r8, WPP_6f3552b14628310eb215fa0007e7d416_Traceguids
0x18000733f  mov     edx, 43h ; 'C'
0x180007344  call    WPP_SF_d
0x180007349  mov     r10, cs:WPP_GLOBAL_Control
0x180007350  jmp     loc_180007235
```
