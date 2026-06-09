# CWerService::_ProcessLpcExceptionMessage(_WERSVC_MSG *,void *)

- ea: `0x18001d380`
- end: `0x18001d5c4`
- name: `?_ProcessLpcExceptionMessage@CWerService@@AEAAJPEAU_WERSVC_MSG@@PEAX@Z`
- size: `580`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *, HANDLE Handle)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x180015d18`

## callees

- `0x1800029d0`
- `0x1800035e8`
- `0x180006a80`
- `0x18001d380`
- `0x18001d5cc`

## import_xrefs

- `ntdll!NtClose` at `0x18001d56c`
- `ntdll!NtClose` at `0x18001d56c`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001d59e`
- `ntdll!NtAlpcSendWaitReceivePort` at `0x18001d59e`

## pseudocode

```c
__int64 __fastcall CWerService::_ProcessLpcExceptionMessage(CWerService *this, struct _WERSVC_MSG *a2, HANDLE Handle)
{
  int v6; // esi
  int v7; // ebx
  __int64 v8; // rdx
  __int16 *v9; // rcx
  struct _WERSVC_MSG *v10; // rax
  __int64 v11; // r8
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  _OWORD *v19; // rax
  __int16 *v20; // rcx
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  HANDLE v29; // rcx
  int v30; // eax
  _OWORD *v31; // rax
  __int16 *v32; // rcx
  __int128 v33; // xmm1
  __int128 v34; // xmm0
  __int128 v35; // xmm1
  __int128 v36; // xmm0
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  __int16 v42; // [rsp+40h] [rbp-148h] BYREF
  _BYTE v43[230]; // [rsp+42h] [rbp-146h] BYREF
  int v44; // [rsp+128h] [rbp-60h]
  char v45; // [rsp+148h] [rbp-40h]

  v42 = 0;
  memset_0(v43, 0, 0x10Eu);
  if ( *((__int16 *)a2 + 2) >= 0 )
  {
    v6 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
    v7 = -2147467259;
    goto LABEL_18;
  }
  v8 = 2;
  v9 = &v42;
  v10 = a2;
  v11 = 2;
  do
  {
    v12 = *((_OWORD *)v10 + 1);
    *(_OWORD *)v9 = *(_OWORD *)v10;
    v13 = *((_OWORD *)v10 + 2);
    *((_OWORD *)v9 + 1) = v12;
    v14 = *((_OWORD *)v10 + 3);
    *((_OWORD *)v9 + 2) = v13;
    v15 = *((_OWORD *)v10 + 4);
    *((_OWORD *)v9 + 3) = v14;
    v16 = *((_OWORD *)v10 + 5);
    *((_OWORD *)v9 + 4) = v15;
    v17 = *((_OWORD *)v10 + 6);
    *((_OWORD *)v9 + 5) = v16;
    v18 = *((_OWORD *)v10 + 7);
    v10 = (struct _WERSVC_MSG *)((char *)v10 + 128);
    *((_OWORD *)v9 + 6) = v17;
    *((_OWORD *)v9 + 7) = v18;
    v9 += 64;
    --v11;
  }
  while ( v11 );
  v6 = 1;
  *(_OWORD *)v9 = *(_OWORD *)v10;
  if ( (v45 & 8) != 0 )
  {
    v19 = (_OWORD *)((char *)a2 + 48);
    v20 = &v42;
    do
    {
      v21 = *((_OWORD *)v20 + 1);
      *v19 = *(_OWORD *)v20;
      v22 = *((_OWORD *)v20 + 2);
      v19[1] = v21;
      v23 = *((_OWORD *)v20 + 3);
      v19[2] = v22;
      v24 = *((_OWORD *)v20 + 4);
      v19[3] = v23;
      v25 = *((_OWORD *)v20 + 5);
      v19[4] = v24;
      v26 = *((_OWORD *)v20 + 6);
      v19[5] = v25;
      v27 = *((_OWORD *)v20 + 7);
      v20 += 64;
      v19[6] = v26;
      v19[7] = v27;
      v19 += 8;
      --v8;
    }
    while ( v8 );
    v28 = *(_OWORD *)v20;
    v29 = 0;
    *v19 = v28;
    v30 = 536870917;
    goto LABEL_17;
  }
  if ( v44 != 1 )
  {
    v31 = (_OWORD *)((char *)a2 + 48);
    v32 = &v42;
    do
    {
      v33 = *((_OWORD *)v32 + 1);
      *v31 = *(_OWORD *)v32;
      v34 = *((_OWORD *)v32 + 2);
      v31[1] = v33;
      v35 = *((_OWORD *)v32 + 3);
      v31[2] = v34;
      v36 = *((_OWORD *)v32 + 4);
      v31[3] = v35;
      v37 = *((_OWORD *)v32 + 5);
      v31[4] = v36;
      v38 = *((_OWORD *)v32 + 6);
      v31[5] = v37;
      v39 = *((_OWORD *)v32 + 7);
      v32 += 64;
      v31[6] = v38;
      v31[7] = v39;
      v31 += 8;
      --v8;
    }
    while ( v8 );
    v40 = *(_OWORD *)v32;
    v29 = Handle;
    *v31 = v40;
    v30 = 536870913;
LABEL_17:
    *((_QWORD *)a2 + 40) = v29;
    *((_DWORD *)a2 + 10) = v30;
    v7 = CWerService::_ProcessRequest(this, a2);
    if ( v7 >= 0 )
      return (unsigned int)v7;
    goto LABEL_18;
  }
  v7 = -2147024846;
LABEL_18:
  if ( Handle )
    NtClose(Handle);
  if ( v6 )
    NtAlpcSendWaitReceivePort(*((_QWORD *)this + 49), 0x10000, &v42, 0, 0, 0, 0, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001d380  push    rbx
0x18001d382  push    rbp
0x18001d383  push    rsi
0x18001d384  push    rdi
0x18001d385  push    r14
0x18001d387  sub     rsp, 160h
0x18001d38e  mov     rax, cs:__security_cookie
0x18001d395  xor     rax, rsp
0x18001d398  mov     [rsp+188h+var_38], rax
0x18001d3a0  mov     rdi, r8
0x18001d3a3  mov     rbx, rdx
0x18001d3a6  mov     rbp, rcx
0x18001d3a9  xor     r14d, r14d
0x18001d3ac  xor     edx, edx; Val
0x18001d3ae  mov     [rsp+188h+var_148], r14w
0x18001d3b4  mov     r8d, 10Eh; Size
0x18001d3ba  lea     rcx, [rsp+188h+var_146]; void *
0x18001d3bf  call    memset_0
0x18001d3c4  cmp     [rbx+4], r14w
0x18001d3c9  jl      short loc_18001D405
0x18001d3cb  mov     esi, r14d
0x18001d3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3d5  lea     rax, WPP_GLOBAL_Control
0x18001d3dc  cmp     rcx, rax
0x18001d3df  jz      short loc_18001D3FB
0x18001d3e1  test    byte ptr [rcx+1Ch], 1
0x18001d3e5  jz      short loc_18001D3FB
0x18001d3e7  mov     rcx, [rcx+10h]
0x18001d3eb  lea     edx, [r14+51h]
0x18001d3ef  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x18001d3f6  call    WPP_SF_
0x18001d3fb  mov     ebx, 80004005h
0x18001d400  jmp     loc_18001D564
0x18001d405  mov     edx, 2
0x18001d40a  lea     rcx, [rsp+188h+var_148]
0x18001d40f  mov     rax, rbx
0x18001d412  mov     r8d, edx
0x18001d415  lea     r9d, [rdx+7Eh]
0x18001d419  movups  xmm0, xmmword ptr [rax]
0x18001d41c  movups  xmm1, xmmword ptr [rax+10h]
0x18001d420  movups  xmmword ptr [rcx], xmm0
0x18001d423  movups  xmm0, xmmword ptr [rax+20h]
0x18001d427  movups  xmmword ptr [rcx+10h], xmm1
0x18001d42b  movups  xmm1, xmmword ptr [rax+30h]
0x18001d42f  movups  xmmword ptr [rcx+20h], xmm0
0x18001d433  movups  xmm0, xmmword ptr [rax+40h]
0x18001d437  movups  xmmword ptr [rcx+30h], xmm1
0x18001d43b  movups  xmm1, xmmword ptr [rax+50h]
0x18001d43f  movups  xmmword ptr [rcx+40h], xmm0
0x18001d443  movups  xmm0, xmmword ptr [rax+60h]
0x18001d447  movups  xmmword ptr [rcx+50h], xmm1
0x18001d44b  movups  xmm1, xmmword ptr [rax+70h]
0x18001d44f  add     rax, r9
0x18001d452  movups  xmmword ptr [rcx+60h], xmm0
0x18001d456  movups  xmmword ptr [rcx+70h], xmm1
0x18001d45a  add     rcx, r9
0x18001d45d  sub     r8, 1
0x18001d461  jnz     short loc_18001D419
0x18001d463  movups  xmm0, xmmword ptr [rax]
0x18001d466  lea     esi, [r8+1]
0x18001d46a  movups  xmmword ptr [rcx], xmm0
0x18001d46d  test    [rsp+188h+var_40], 8
0x18001d475  jz      short loc_18001D4D9
0x18001d477  lea     rax, [rbx+30h]
0x18001d47b  lea     rcx, [rsp+188h+var_148]
0x18001d480  movups  xmm0, xmmword ptr [rcx]
0x18001d483  movups  xmm1, xmmword ptr [rcx+10h]
0x18001d487  movups  xmmword ptr [rax], xmm0
0x18001d48a  movups  xmm0, xmmword ptr [rcx+20h]
0x18001d48e  movups  xmmword ptr [rax+10h], xmm1
0x18001d492  movups  xmm1, xmmword ptr [rcx+30h]
0x18001d496  movups  xmmword ptr [rax+20h], xmm0
0x18001d49a  movups  xmm0, xmmword ptr [rcx+40h]
0x18001d49e  movups  xmmword ptr [rax+30h], xmm1
0x18001d4a2  movups  xmm1, xmmword ptr [rcx+50h]
0x18001d4a6  movups  xmmword ptr [rax+40h], xmm0
0x18001d4aa  movups  xmm0, xmmword ptr [rcx+60h]
0x18001d4ae  movups  xmmword ptr [rax+50h], xmm1
0x18001d4b2  movups  xmm1, xmmword ptr [rcx+70h]
0x18001d4b6  add     rcx, r9
0x18001d4b9  movups  xmmword ptr [rax+60h], xmm0
0x18001d4bd  movups  xmmword ptr [rax+70h], xmm1
0x18001d4c1  add     rax, r9
0x18001d4c4  sub     rdx, rsi
0x18001d4c7  jnz     short loc_18001D480
0x18001d4c9  movups  xmm0, xmmword ptr [rcx]
0x18001d4cc  mov     rcx, r14
0x18001d4cf  movups  xmmword ptr [rax], xmm0
0x18001d4d2  mov     eax, 20000005h
0x18001d4d7  jmp     short loc_18001D549
0x18001d4d9  cmp     [rsp+188h+var_60], esi
0x18001d4e0  jnz     short loc_18001D4E9
0x18001d4e2  mov     ebx, 80070032h
0x18001d4e7  jmp     short loc_18001D564
0x18001d4e9  lea     rax, [rbx+30h]
0x18001d4ed  lea     rcx, [rsp+188h+var_148]
0x18001d4f2  movups  xmm0, xmmword ptr [rcx]
0x18001d4f5  movups  xmm1, xmmword ptr [rcx+10h]
0x18001d4f9  movups  xmmword ptr [rax], xmm0
0x18001d4fc  movups  xmm0, xmmword ptr [rcx+20h]
0x18001d500  movups  xmmword ptr [rax+10h], xmm1
0x18001d504  movups  xmm1, xmmword ptr [rcx+30h]
0x18001d508  movups  xmmword ptr [rax+20h], xmm0
0x18001d50c  movups  xmm0, xmmword ptr [rcx+40h]
0x18001d510  movups  xmmword ptr [rax+30h], xmm1
0x18001d514  movups  xmm1, xmmword ptr [rcx+50h]
0x18001d518  movups  xmmword ptr [rax+40h], xmm0
0x18001d51c  movups  xmm0, xmmword ptr [rcx+60h]
0x18001d520  movups  xmmword ptr [rax+50h], xmm1
0x18001d524  movups  xmm1, xmmword ptr [rcx+70h]
0x18001d528  add     rcx, r9
0x18001d52b  movups  xmmword ptr [rax+60h], xmm0
0x18001d52f  movups  xmmword ptr [rax+70h], xmm1
0x18001d533  add     rax, r9
0x18001d536  sub     rdx, rsi
0x18001d539  jnz     short loc_18001D4F2
0x18001d53b  movups  xmm0, xmmword ptr [rcx]
0x18001d53e  mov     rcx, rdi
0x18001d541  movups  xmmword ptr [rax], xmm0
0x18001d544  mov     eax, 20000001h
0x18001d549  mov     [rbx+140h], rcx
0x18001d550  mov     rdx, rbx; struct _WERSVC_MSG *
0x18001d553  mov     rcx, rbp; this
0x18001d556  mov     [rbx+28h], eax
0x18001d559  call    ?_ProcessRequest@CWerService@@AEAAJPEAU_WERSVC_MSG@@@Z; CWerService::_ProcessRequest(_WERSVC_MSG *)
0x18001d55e  mov     ebx, eax
0x18001d560  test    eax, eax
0x18001d562  jns     short loc_18001D5A4
0x18001d564  test    rdi, rdi
0x18001d567  jz      short loc_18001D572
0x18001d569  mov     rcx, rdi; Handle
0x18001d56c  call    cs:__imp_NtClose
0x18001d572  test    esi, esi
0x18001d574  jz      short loc_18001D5A4
0x18001d576  mov     rcx, [rbp+188h]
0x18001d57d  lea     r8, [rsp+188h+var_148]
0x18001d582  mov     [rsp+188h+var_150], r14
0x18001d587  xor     r9d, r9d
0x18001d58a  mov     [rsp+188h+var_158], r14
0x18001d58f  mov     edx, 10000h
0x18001d594  mov     [rsp+188h+var_160], r14
0x18001d599  mov     [rsp+188h+var_168], r14
0x18001d59e  call    cs:__imp_NtAlpcSendWaitReceivePort
0x18001d5a4  mov     eax, ebx
0x18001d5a6  mov     rcx, [rsp+188h+var_38]
0x18001d5ae  xor     rcx, rsp; StackCookie
0x18001d5b1  call    __security_check_cookie
0x18001d5b6  add     rsp, 160h
0x18001d5bd  pop     r14
0x18001d5bf  pop     rdi
0x18001d5c0  pop     rsi
0x18001d5c1  pop     rbp
0x18001d5c2  pop     rbx
0x18001d5c3  retn
```
