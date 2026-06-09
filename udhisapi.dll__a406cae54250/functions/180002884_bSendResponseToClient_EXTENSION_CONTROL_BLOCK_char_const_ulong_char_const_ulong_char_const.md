# bSendResponseToClient(_EXTENSION_CONTROL_BLOCK *,char const *,ulong,char const *,ulong,char const *)

- ea: `0x180002884`
- end: `0x180002a49`
- name: `?bSendResponseToClient@@YAHPEAU_EXTENSION_CONTROL_BLOCK@@PEBDK1K1@Z`
- size: `453`
- prototype: `__int64 __fastcall(struct _EXTENSION_CONTROL_BLOCK *, const char *, unsigned int, const char *, unsigned int, const char *)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800026a4`
- `0x180002af0`
- `0x180002f08`
- `0x180003aa0`
- `0x180006868`

## callees

- `0x1800024c4`
- `0x180002884`
- `0x180002a50`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800029f0`

## pseudocode

```c
__int64 __fastcall bSendResponseToClient(
        struct _EXTENSION_CONTROL_BLOCK *a1,
        const char *a2,
        unsigned int a3,
        const char *a4,
        unsigned int a5,
        const char *a6)
{
  HCONN ConnID; // rcx
  BOOL (__stdcall *ServerSupportFunction)(HCONN, DWORD, LPVOID, LPDWORD, LPDWORD); // rax
  int v12; // r8d
  const char *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  const char *v16; // rdi
  BOOL (__stdcall *v17)(HCONN, DWORD, LPVOID, LPDWORD, LPDWORD); // rax
  HCONN v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  HCONN v21; // rcx
  _QWORD *v22; // rcx
  DWORD LastError; // eax
  __int64 v24; // rdx
  _QWORD v26[2]; // [rsp+30h] [rbp-28h] BYREF
  __int128 v27; // [rsp+40h] [rbp-18h]
  unsigned int v28; // [rsp+A0h] [rbp+48h] BYREF

  v28 = 0;
  ConnID = a1->ConnID;
  ServerSupportFunction = a1->ServerSupportFunction;
  v27 = 0;
  ((void (__fastcall *)(HCONN, __int64, unsigned int *, _QWORD, _QWORD))ServerSupportFunction)(ConnID, 1008, &v28, 0, 0);
  v26[0] = a2;
  v26[1] = a4;
  *(_QWORD *)((char *)&v27 + 4) = __PAIR64__(v28, a3);
  if ( !a2 )
    goto LABEL_6;
  v13 = a2;
  v14 = 0x7FFFFFFF;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v14;
  }
  while ( v14 );
  v12 = 0x7FFFFFFF - v14;
  v15 = (0x7FFFFFFF - v14) & ((unsigned __int128)-(__int128)(unsigned __int64)v14 >> 64);
  if ( !v14 )
LABEL_6:
    LODWORD(v15) = 0;
  LODWORD(v27) = v15;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, v12, (_DWORD)a2, (__int64)a4);
  v16 = a6;
  v17 = a1->ServerSupportFunction;
  v18 = a1->ConnID;
  if ( a6 )
    v19 = ((__int64 (__fastcall *)(HCONN, __int64, _QWORD *, unsigned int *, const char *))v17)(v18, 1016, v26, &a5, a6);
  else
    v19 = ((__int64 (__fastcall *)(HCONN, __int64, _QWORD *, _QWORD, _QWORD))v17)(v18, 1016, v26, 0, 0);
  v20 = v19;
  if ( !v19 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return v20;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    LastError = GetLastError();
    v24 = 12;
    goto LABEL_22;
  }
  if ( !v16 )
    goto LABEL_23;
  v21 = a1->ConnID;
  LODWORD(a6) = a5;
  v20 = ((__int64 (__fastcall *)(HCONN, const char *, const char **, __int64))a1->WriteClient)(v21, v16, &a6, 1);
  if ( v20 )
    goto LABEL_23;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return v20;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    v24 = 11;
LABEL_22:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, WPP_23ee521612fa330e734a633d49cd7b43_Traceguids, LastError);
LABEL_23:
    v22 = WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( v22 != &WPP_GLOBAL_Control && (*((_DWORD *)v22 + 7) & 0x400) != 0 )
    WPP_SF_d(v22[2], 13, WPP_23ee521612fa330e734a633d49cd7b43_Traceguids, v20);
  return v20;
}

```

## disassembly

```asm
0x180002884  push    rbp
0x180002886  push    rbx
0x180002887  push    rsi
0x180002888  push    rdi
0x180002889  push    r12
0x18000288b  push    r14
0x18000288d  mov     rbp, rsp
0x180002890  sub     rsp, 58h
0x180002894  mov     rsi, rcx
0x180002897  mov     [rbp+arg_10], 0
0x18000289e  mov     rcx, [rcx+8]
0x1800028a2  xorps   xmm0, xmm0
0x1800028a5  mov     r14, r9
0x1800028a8  mov     [rsp+58h+var_38], 0
0x1800028b1  mov     ebx, r8d
0x1800028b4  mov     rdi, rdx
0x1800028b7  mov     rax, [rsi+0B8h]
0x1800028be  lea     r8, [rbp+arg_10]
0x1800028c2  xor     r9d, r9d
0x1800028c5  mov     edx, 3F0h
0x1800028ca  movups  [rbp+var_28], xmm0
0x1800028ce  movups  [rbp+var_18], xmm0
0x1800028d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d7  mov     eax, [rbp+arg_10]
0x1800028da  mov     dword ptr [rbp+var_18+8], eax
0x1800028dd  mov     qword ptr [rbp+var_28], rdi
0x1800028e1  mov     qword ptr [rbp+var_28+8], r14
0x1800028e5  mov     dword ptr [rbp+var_18+4], ebx
0x1800028e8  test    rdi, rdi
0x1800028eb  jz      short loc_18000291B
0x1800028ed  mov     r8d, 7FFFFFFFh
0x1800028f3  mov     rax, rdi
0x1800028f6  mov     ecx, r8d
0x1800028f9  cmp     byte ptr [rax], 0
0x1800028fc  jz      short loc_180002907
0x1800028fe  inc     rax
0x180002901  sub     rcx, 1
0x180002905  jnz     short loc_1800028F9
0x180002907  sub     r8, rcx
0x18000290a  mov     rax, rcx
0x18000290d  neg     rax
0x180002910  sbb     rdx, rdx
0x180002913  and     rdx, r8
0x180002916  test    rcx, rcx
0x180002919  jnz     short loc_18000291D
0x18000291b  xor     edx, edx
0x18000291d  mov     dword ptr [rbp+var_18], edx
0x180002920  mov     rcx, cs:WPP_GLOBAL_Control
0x180002927  lea     r12, WPP_GLOBAL_Control
0x18000292e  cmp     rcx, r12
0x180002931  jz      short loc_18000294D
0x180002933  test    dword ptr [rcx+1Ch], 400h
0x18000293a  jz      short loc_18000294D
0x18000293c  mov     rcx, [rcx+10h]
0x180002940  mov     r9, rdi
0x180002943  mov     [rsp+58h+var_38], r14
0x180002948  call    WPP_SF_ss
0x18000294d  mov     rdi, [rbp+arg_28]
0x180002951  lea     r8, [rbp+var_28]
0x180002955  mov     rax, [rsi+0B8h]
0x18000295c  mov     edx, 3F8h
0x180002961  mov     rcx, [rsi+8]
0x180002965  test    rdi, rdi
0x180002968  jz      short loc_180002975
0x18000296a  mov     [rsp+58h+var_38], rdi
0x18000296f  lea     r9, [rbp+arg_20]
0x180002973  jmp     short loc_180002981
0x180002975  mov     [rsp+58h+var_38], 0
0x18000297e  xor     r9d, r9d
0x180002981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002986  lea     r14, WPP_23ee521612fa330e734a633d49cd7b43_Traceguids
0x18000298d  mov     ebx, eax
0x18000298f  test    eax, eax
0x180002991  jz      short loc_1800029DE
0x180002993  test    rdi, rdi
0x180002996  jz      short loc_180002A11
0x180002998  mov     eax, [rbp+arg_20]
0x18000299b  lea     r8, [rbp+arg_28]
0x18000299f  mov     rcx, [rsi+8]
0x1800029a3  mov     r9d, 1
0x1800029a9  mov     dword ptr [rbp+arg_28], eax
0x1800029ac  mov     rdx, rdi
0x1800029af  mov     rax, [rsi+0A8h]
0x1800029b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029bb  mov     ebx, eax
0x1800029bd  test    eax, eax
0x1800029bf  jnz     short loc_180002A11
0x1800029c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029c8  cmp     rcx, r12
0x1800029cb  jz      short loc_180002A3A
0x1800029cd  test    byte ptr [rcx+1Ch], 1
0x1800029d1  jz      short loc_180002A18
0x1800029d3  call    cs:__imp_GetLastError
0x1800029d9  lea     edx, [rbx+0Bh]
0x1800029dc  jmp     short loc_1800029FB
0x1800029de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029e5  cmp     rcx, r12
0x1800029e8  jz      short loc_180002A3A
0x1800029ea  test    byte ptr [rcx+1Ch], 1
0x1800029ee  jz      short loc_180002A18
0x1800029f0  call    cs:__imp_GetLastError
0x1800029f6  mov     edx, 0Ch
0x1800029fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a02  mov     r9d, eax
0x180002a05  mov     r8, r14
0x180002a08  mov     rcx, [rcx+10h]
0x180002a0c  call    WPP_SF_d
0x180002a11  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a18  cmp     rcx, r12
0x180002a1b  jz      short loc_180002A3A
0x180002a1d  test    dword ptr [rcx+1Ch], 400h
0x180002a24  jz      short loc_180002A3A
0x180002a26  mov     rcx, [rcx+10h]
0x180002a2a  mov     edx, 0Dh
0x180002a2f  mov     r9d, ebx
0x180002a32  mov     r8, r14
0x180002a35  call    WPP_SF_d
0x180002a3a  mov     eax, ebx
0x180002a3c  add     rsp, 58h
0x180002a40  pop     r14
0x180002a42  pop     r12
0x180002a44  pop     rdi
0x180002a45  pop     rsi
0x180002a46  pop     rbx
0x180002a47  pop     rbp
0x180002a48  retn
```
