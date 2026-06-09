# WaitForStop(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS *,ulong,ulong)

- ea: `0x14004a240`
- end: `0x14004a488`
- name: `?WaitForStop@@YAKPEAUSC_HANDLE__@@PEAU_SERVICE_STATUS_PROCESS@@KK@Z`
- size: `584`
- prototype: `unsigned int __fastcall(SC_HANDLE hService, LPBYTE lpBuffer, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140049898`

## callees

- `0x14003f17c`
- `0x140047798`
- `0x14004a240`
- `0x14004a500`
- `0x14004a9d0`

## import_xrefs

- `ADVAPI32!QueryServiceStatusEx` at `0x14004a34d`
- `ADVAPI32!QueryServiceStatusEx` at `0x14004a34d`
- `KERNEL32!GetTickCount` at `0x14004a361`
- `KERNEL32!GetTickCount` at `0x14004a3a1`
- `KERNEL32!GetTickCount` at `0x14004a361`
- `KERNEL32!GetTickCount` at `0x14004a3a1`
- `KERNEL32!Sleep` at `0x14004a32c`
- `KERNEL32!Sleep` at `0x14004a32c`
- `KERNEL32!GetLastError` at `0x14004a3fd`
- `KERNEL32!GetLastError` at `0x14004a3fd`

## pseudocode

```c
__int64 __fastcall WaitForStop(SC_HANDLE hService, BYTE *lpBuffer, __int64 a3, DWORD a4)
{
  unsigned int v4; // ebp
  PVOID *v7; // r10
  unsigned int v8; // ebx
  DWORD v9; // edi
  DWORD TickCount; // eax
  DWORD LastError; // eax
  DWORD pcbBytesNeeded; // [rsp+88h] [rbp+20h] BYREF

  pcbBytesNeeded = a4;
  v4 = a3;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqDD(*((_QWORD *)WPP_GLOBAL_Control + 2), lpBuffer, a3, hService, lpBuffer, a3);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  pcbBytesNeeded = 0;
  v8 = 0;
  if ( v7 == &WPP_GLOBAL_Control || (*((_BYTE *)v7 + 28) & 2) == 0 || *((_BYTE *)v7 + 25) < 5u )
    goto LABEL_10;
  WPP_SF_(v7[2], 51, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
  while ( 1 )
  {
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_10:
    if ( *((_DWORD *)lpBuffer + 1) == 1 )
      goto LABEL_36;
    v9 = *((_DWORD *)lpBuffer + 6);
    if ( v9 >= 0x7530 )
    {
      v9 = 30000;
    }
    else if ( v9 < 0x1F4 )
    {
      v9 = 500;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 2) != 0 && *((_BYTE *)v7 + 25) >= 5u )
      WPP_SF_d(v7[2], 52, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v9);
    Sleep(v9);
    if ( !QueryServiceStatusEx(hService, SC_STATUS_PROCESS_INFO, lpBuffer, 0x24u, &pcbBytesNeeded) )
    {
      LastError = GetLastError();
      v8 = LastError;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, LastError);
        goto LABEL_35;
      }
      goto LABEL_36;
    }
    if ( *((_DWORD *)lpBuffer + 1) == 1 )
      break;
    if ( GetTickCount() - v4 > 0x7530 )
    {
      v8 = 1460;
      v7 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v8;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        TickCount = GetTickCount();
        WPP_SF_DDd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids,
          v4,
          TickCount,
          30000);
LABEL_35:
        v7 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_36;
      }
      goto LABEL_36;
    }
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v8;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids);
    goto LABEL_35;
  }
LABEL_36:
  if ( v7 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v7 + 28) & 1) != 0
    && *((unsigned __int8 *)v7 + 25) >= (unsigned int)(v8 != 0 ? 2 : 5) )
  {
    WPP_SF_d(v7[2], 56, &WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x14004a240  mov     rax, rsp
0x14004a243  mov     [rax+8], rbx
0x14004a247  mov     [rax+10h], rbp
0x14004a24b  mov     [rax+20h], r9d
0x14004a24f  push    rsi
0x14004a250  push    rdi
0x14004a251  push    r12
0x14004a253  push    r13
0x14004a255  push    r14
0x14004a257  sub     rsp, 40h
0x14004a25b  mov     ebp, r8d
0x14004a25e  mov     rsi, rdx
0x14004a261  mov     r14, rcx
0x14004a264  mov     r10, cs:WPP_GLOBAL_Control
0x14004a26b  lea     r12, WPP_GLOBAL_Control
0x14004a272  cmp     r10, r12
0x14004a275  jz      short loc_14004A2A0
0x14004a277  test    byte ptr [r10+1Ch], 1
0x14004a27c  jz      short loc_14004A2A0
0x14004a27e  cmp     byte ptr [r10+19h], 5
0x14004a283  jb      short loc_14004A2A0
0x14004a285  mov     r9, rcx
0x14004a288  mov     [rax-40h], r8d
0x14004a28c  mov     rcx, [r10+10h]
0x14004a290  mov     [rax-48h], rdx
0x14004a294  call    WPP_SF_qqDD
0x14004a299  mov     r10, cs:WPP_GLOBAL_Control
0x14004a2a0  mov     [rsp+68h+arg_18], 0
0x14004a2ab  xor     ebx, ebx
0x14004a2ad  lea     r13, WPP_938229fa298d3f12b2cbdbc44a39d398_Traceguids
0x14004a2b4  cmp     r10, r12
0x14004a2b7  jz      short loc_14004A2DD
0x14004a2b9  test    byte ptr [r10+1Ch], 2
0x14004a2be  jz      short loc_14004A2DD
0x14004a2c0  cmp     byte ptr [r10+19h], 5
0x14004a2c5  jb      short loc_14004A2DD
0x14004a2c7  mov     rcx, [r10+10h]
0x14004a2cb  lea     edx, [rbx+33h]
0x14004a2ce  mov     r8, r13
0x14004a2d1  call    WPP_SF_
0x14004a2d6  mov     r10, cs:WPP_GLOBAL_Control
0x14004a2dd  cmp     dword ptr [rsi+4], 1
0x14004a2e1  mov     eax, 1F4h
0x14004a2e6  jz      loc_14004A43A
0x14004a2ec  mov     edi, [rsi+18h]
0x14004a2ef  cmp     edi, 7530h
0x14004a2f5  jnb     short loc_14004A2FE
0x14004a2f7  cmp     edi, eax
0x14004a2f9  cmovb   edi, eax
0x14004a2fc  jmp     short loc_14004A303
0x14004a2fe  mov     edi, 7530h
0x14004a303  cmp     r10, r12
0x14004a306  jz      short loc_14004A32A
0x14004a308  test    byte ptr [r10+1Ch], 2
0x14004a30d  jz      short loc_14004A32A
0x14004a30f  cmp     byte ptr [r10+19h], 5
0x14004a314  jb      short loc_14004A32A
0x14004a316  mov     rcx, [r10+10h]
0x14004a31a  mov     edx, 34h ; '4'
0x14004a31f  mov     r9d, edi
0x14004a322  mov     r8, r13
0x14004a325  call    WPP_SF_d
0x14004a32a  mov     ecx, edi; dwMilliseconds
0x14004a32c  call    cs:__imp_Sleep
0x14004a332  lea     rax, [rsp+68h+arg_18]
0x14004a33a  mov     r9d, 24h ; '$'; cbBufSize
0x14004a340  mov     r8, rsi; lpBuffer
0x14004a343  mov     [rsp+68h+pcbBytesNeeded], rax; pcbBytesNeeded
0x14004a348  xor     edx, edx; InfoLevel
0x14004a34a  mov     rcx, r14; hService
0x14004a34d  call    cs:__imp_QueryServiceStatusEx
0x14004a353  test    eax, eax
0x14004a355  jz      loc_14004A3FD
0x14004a35b  cmp     dword ptr [rsi+4], 1
0x14004a35f  jz      short loc_14004A3CC
0x14004a361  call    cs:__imp_GetTickCount
0x14004a367  sub     eax, ebp
0x14004a369  mov     edi, 7530h
0x14004a36e  cmp     eax, edi
0x14004a370  jbe     loc_14004A2D6
0x14004a376  mov     ebx, 5B4h
0x14004a37b  mov     r10, cs:WPP_GLOBAL_Control
0x14004a382  cmp     r10, r12
0x14004a385  jz      loc_14004A46F
0x14004a38b  test    byte ptr [r10+1Ch], 2
0x14004a390  jz      loc_14004A43A
0x14004a396  cmp     byte ptr [r10+19h], 2
0x14004a39b  jb      loc_14004A43A
0x14004a3a1  call    cs:__imp_GetTickCount
0x14004a3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14004a3ae  mov     edx, 37h ; '7'
0x14004a3b3  mov     [rsp+68h+var_40], edi
0x14004a3b7  mov     r9d, ebp
0x14004a3ba  mov     r8, r13
0x14004a3bd  mov     dword ptr [rsp+68h+pcbBytesNeeded], eax
0x14004a3c1  mov     rcx, [rcx+10h]
0x14004a3c5  call    WPP_SF_DDd
0x14004a3ca  jmp     short loc_14004A433
0x14004a3cc  mov     r10, cs:WPP_GLOBAL_Control
0x14004a3d3  cmp     r10, r12
0x14004a3d6  jz      loc_14004A46F
0x14004a3dc  test    byte ptr [r10+1Ch], 2
0x14004a3e1  jz      short loc_14004A43A
0x14004a3e3  cmp     byte ptr [r10+19h], 5
0x14004a3e8  jb      short loc_14004A43A
0x14004a3ea  mov     rcx, [r10+10h]
0x14004a3ee  mov     edx, 36h ; '6'
0x14004a3f3  mov     r8, r13
0x14004a3f6  call    WPP_SF_
0x14004a3fb  jmp     short loc_14004A433
0x14004a3fd  call    cs:__imp_GetLastError
0x14004a403  mov     ebx, eax
0x14004a405  mov     r10, cs:WPP_GLOBAL_Control
0x14004a40c  cmp     r10, r12
0x14004a40f  jz      short loc_14004A46F
0x14004a411  test    byte ptr [r10+1Ch], 2
0x14004a416  jz      short loc_14004A43A
0x14004a418  cmp     byte ptr [r10+19h], 2
0x14004a41d  jb      short loc_14004A43A
0x14004a41f  mov     rcx, [r10+10h]
0x14004a423  mov     edx, 35h ; '5'
0x14004a428  mov     r9d, eax
0x14004a42b  mov     r8, r13
0x14004a42e  call    WPP_SF_d
0x14004a433  mov     r10, cs:WPP_GLOBAL_Control
0x14004a43a  cmp     r10, r12
0x14004a43d  jz      short loc_14004A46F
0x14004a43f  test    byte ptr [r10+1Ch], 1
0x14004a444  jz      short loc_14004A46F
0x14004a446  movzx   edx, byte ptr [r10+19h]
0x14004a44b  mov     eax, ebx
0x14004a44d  neg     eax
0x14004a44f  sbb     ecx, ecx
0x14004a451  and     ecx, 0FFFFFFFDh
0x14004a454  add     ecx, 5
0x14004a457  cmp     edx, ecx
0x14004a459  jb      short loc_14004A46F
0x14004a45b  mov     rcx, [r10+10h]
0x14004a45f  mov     edx, 38h ; '8'
0x14004a464  mov     r9d, ebx
0x14004a467  mov     r8, r13
0x14004a46a  call    WPP_SF_d
0x14004a46f  mov     rbp, [rsp+68h+arg_8]
0x14004a474  mov     eax, ebx
0x14004a476  mov     rbx, [rsp+68h+arg_0]
0x14004a47b  add     rsp, 40h
0x14004a47f  pop     r14
0x14004a481  pop     r13
0x14004a483  pop     r12
0x14004a485  pop     rdi
0x14004a486  pop     rsi
0x14004a487  retn
```
