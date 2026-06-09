# RtmDeleteRoute

- ea: `0x1800102d0`
- end: `0x18001053c`
- name: `RtmDeleteRoute`
- size: `620`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000e7a0`
- `0x18000ecec`
- `0x1800102d0`
- `0x18001163c`
- `0x180011800`
- `0x18001f946`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall RtmDeleteRoute(__int64 a1, _DWORD *a2, _DWORD *a3, void *a4)
{
  unsigned int v6; // r10d
  __int64 *v7; // rbx
  __int64 v8; // rdi
  __int64 *v10; // r14
  __int64 *v11; // rsi
  __int64 v12; // r12
  __int64 *i; // rdi
  int v14; // eax
  int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // edx
  unsigned int v18; // r9d
  __int64 v19; // rax
  unsigned int v20; // edi
  __int64 v21; // [rsp+30h] [rbp-38h]

  v6 = *(_DWORD *)(a1 + 16) ^ 0x52544D00;
  v7 = &Tables[48 * v6];
  if ( v6 )
    return 6;
  if ( _InterlockedAdd((volatile signed __int32 *)v7 + 2, 1u) <= 0 )
  {
    _InterlockedDecrement((volatile signed __int32 *)v7 + 2);
    return 6;
  }
  a2[2] = *(_DWORD *)(a1 + 20);
  v8 = 32LL * ((int (__fastcall *)(_DWORD *))v7[40])(a2 + 8) + v7[32];
  v21 = v8;
  if ( DoEnterSyncList((__int64)v7, v8, 1) )
  {
    v10 = 0;
    v11 = 0;
    v12 = v8 + 16;
    for ( i = *(__int64 **)(v8 + 16); i != (__int64 *)v12; i = (__int64 *)*i )
    {
      if ( (i[8] & 1) == 0 )
      {
        v14 = ((__int64 (__fastcall *)(_DWORD *, __int64))v7[36])(a2 + 8, (__int64)i + 116);
        if ( v14 )
        {
          if ( v14 < 0 )
            break;
        }
        else if ( v10
               || a2[3] != *((_DWORD *)i + 24)
               || a2[2] != *((_DWORD *)i + 23)
               || ((unsigned int (__fastcall *)(_DWORD *, __int64))v7[37])(a2, (__int64)i + 84) )
        {
          if ( (i[8] & 4) != 0
            && (!v11 || ((int (__fastcall *)(__int64, __int64))v7[39])((__int64)v11 + 84, (__int64)i + 84) > 0) )
          {
            v11 = i;
          }
        }
        else
        {
          v10 = i;
          if ( (i[8] & 2) == 0 )
            break;
        }
      }
    }
    if ( v10 )
    {
      v15 = *((_DWORD *)v10 + 16);
      if ( (v15 & 2) != 0 )
      {
        if ( !v11 )
        {
          _InterlockedDecrement((volatile signed __int32 *)v7 + 9);
          *a3 = 2;
          NotifyClients(v7, a1, 2, 0, (char *)v10 + 84);
          v16 = 0;
          v17 = 32;
          v18 = a2[9];
          while ( 1 )
          {
            v19 = (v17 + v16) >> 1;
            if ( *(_DWORD *)&g_meMaskTable[8 * v19] >= v18 )
            {
              if ( *(_DWORD *)&g_meMaskTable[8 * v19] <= v18 )
              {
                _InterlockedDecrement((volatile signed __int32 *)&g_meMaskTable[8 * v19 + 4]);
                goto LABEL_36;
              }
              v17 = v19 - 1;
            }
            else
            {
              v16 = v19 + 1;
            }
            if ( v16 > v17 )
              goto LABEL_36;
          }
        }
        *((_DWORD *)v10 + 16) = v15 & 0xFFFFFFFD;
        *((_DWORD *)v11 + 16) |= 2u;
        *a3 = 3;
        if ( a4 )
          memcpy_0(a4, (char *)v11 + 84, *((int *)v7 + 70));
        NotifyClients(v7, a1, (unsigned int)*a3, (char *)v11 + 84, (char *)v10 + 84);
      }
      else
      {
        *a3 = 0;
      }
LABEL_36:
      v20 = RemoveRouteNode(v7);
    }
    else
    {
      v20 = 259;
    }
    LeaveSyncList(v7, v21);
    _InterlockedDecrement((volatile signed __int32 *)v7 + 2);
    return v20;
  }
  else
  {
    _InterlockedDecrement((volatile signed __int32 *)v7 + 2);
    return 1450;
  }
}

```

## disassembly

```asm
0x1800102d0  mov     r11, rsp
0x1800102d3  mov     [r11+10h], rbx
0x1800102d7  mov     [r11+18h], rsi
0x1800102db  mov     [r11+20h], r9
0x1800102df  mov     [r11+8], rcx
0x1800102e3  push    rdi
0x1800102e4  push    r12
0x1800102e6  push    r13
0x1800102e8  push    r14
0x1800102ea  push    r15
0x1800102ec  sub     rsp, 40h
0x1800102f0  mov     r15, r8
0x1800102f3  mov     r13, rdx
0x1800102f6  mov     eax, [rcx+10h]
0x1800102f9  xor     eax, 52544D00h
0x1800102fe  mov     r10d, eax
0x180010301  lea     rbx, [rax+rax*2]
0x180010305  shl     rbx, 7
0x180010309  lea     rax, Tables
0x180010310  add     rbx, rax
0x180010313  mov     [r11-30h], rbx
0x180010317  cmp     r10d, 1
0x18001031b  jnb     loc_180010516
0x180010321  lock add dword ptr [rbx+8], 1
0x180010326  jle     loc_180010512
0x18001032c  mov     eax, [rcx+14h]
0x18001032f  mov     [rdx+8], eax
0x180010332  lea     rcx, [rdx+20h]
0x180010336  mov     rax, [rbx+140h]
0x18001033d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010342  movsxd  rcx, eax
0x180010345  shl     rcx, 5
0x180010349  mov     rdi, [rbx+100h]
0x180010350  add     rdi, rcx
0x180010353  mov     [rsp+68h+var_38], rdi
0x180010358  mov     r8b, 1
0x18001035b  mov     rdx, rdi
0x18001035e  mov     rcx, rbx
0x180010361  call    DoEnterSyncList
0x180010366  test    al, al
0x180010368  jnz     short loc_180010378
0x18001036a  lock dec dword ptr [rbx+8]
0x18001036e  mov     eax, 5AAh
0x180010373  jmp     loc_180010522
0x180010378  xor     r14d, r14d
0x18001037b  xor     esi, esi
0x18001037d  lea     r12, [rdi+10h]
0x180010381  mov     rdi, [r12]
0x180010385  jmp     loc_18001040E
0x18001038a  test    byte ptr [rdi+40h], 1
0x18001038e  jnz     short loc_18001040B
0x180010390  lea     rdx, [rdi+74h]
0x180010394  lea     rcx, [r13+20h]
0x180010398  mov     rax, [rbx+120h]
0x18001039f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103a4  test    eax, eax
0x1800103a6  jnz     short loc_180010409
0x1800103a8  test    r14, r14
0x1800103ab  jnz     short loc_1800103E1
0x1800103ad  mov     eax, [rdi+60h]
0x1800103b0  cmp     [r13+0Ch], eax
0x1800103b4  jnz     short loc_1800103E1
0x1800103b6  mov     eax, [rdi+5Ch]
0x1800103b9  cmp     [r13+8], eax
0x1800103bd  jnz     short loc_1800103E1
0x1800103bf  lea     rdx, [rdi+54h]
0x1800103c3  mov     rcx, r13
0x1800103c6  mov     rax, [rbx+128h]
0x1800103cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103d2  test    eax, eax
0x1800103d4  jnz     short loc_1800103E1
0x1800103d6  mov     r14, rdi
0x1800103d9  test    byte ptr [rdi+40h], 2
0x1800103dd  jz      short loc_180010417
0x1800103df  jmp     short loc_18001040B
0x1800103e1  test    byte ptr [rdi+40h], 4
0x1800103e5  jz      short loc_18001040B
0x1800103e7  test    rsi, rsi
0x1800103ea  jz      short loc_180010404
0x1800103ec  lea     rdx, [rdi+54h]
0x1800103f0  lea     rcx, [rsi+54h]
0x1800103f4  mov     rax, [rbx+138h]
0x1800103fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010400  test    eax, eax
0x180010402  jle     short loc_18001040B
0x180010404  mov     rsi, rdi
0x180010407  jmp     short loc_18001040B
0x180010409  js      short loc_180010417
0x18001040b  mov     rdi, [rdi]
0x18001040e  cmp     rdi, r12
0x180010411  jnz     loc_18001038A
0x180010417  test    r14, r14
0x18001041a  jz      loc_1800104F8
0x180010420  mov     eax, [r14+40h]
0x180010424  test    al, 2
0x180010426  jz      loc_1800104E2
0x18001042c  test    rsi, rsi
0x18001042f  jz      short loc_180010482
0x180010431  and     eax, 0FFFFFFFDh
0x180010434  mov     [r14+40h], eax
0x180010438  or      dword ptr [rsi+40h], 2
0x18001043c  mov     dword ptr [r15], 3
0x180010443  mov     rax, [rsp+68h+arg_18]
0x18001044b  test    rax, rax
0x18001044e  jz      short loc_180010463
0x180010450  movsxd  r8, dword ptr [rbx+118h]; Size
0x180010457  lea     rdx, [rsi+54h]; Src
0x18001045b  mov     rcx, rax; void *
0x18001045e  call    memcpy_0
0x180010463  lea     rax, [r14+54h]
0x180010467  lea     r9, [rsi+54h]
0x18001046b  mov     [rsp+68h+var_48], rax
0x180010470  mov     r8d, [r15]
0x180010473  mov     rdx, [rsp+68h+arg_0]
0x180010478  mov     rcx, rbx
0x18001047b  call    NotifyClients
0x180010480  jmp     short loc_1800104E9
0x180010482  lock dec dword ptr [rbx+24h]
0x180010486  mov     dword ptr [r15], 2
0x18001048d  lea     rax, [r14+54h]
0x180010491  mov     [rsp+68h+var_48], rax
0x180010496  xor     r9d, r9d
0x180010499  lea     r8d, [r9+2]
0x18001049d  mov     rdx, [rsp+68h+arg_0]
0x1800104a2  mov     rcx, rbx
0x1800104a5  call    NotifyClients
0x1800104aa  xor     r8d, r8d
0x1800104ad  lea     edx, [r8+20h]
0x1800104b1  mov     r9d, [r13+24h]
0x1800104b5  lea     r10, g_meMaskTable
0x1800104bc  lea     eax, [rdx+r8]
0x1800104c0  shr     eax, 1
0x1800104c2  cmp     [r10+rax*8], r9d
0x1800104c6  jnb     short loc_1800104CE
0x1800104c8  lea     r8d, [rax+1]
0x1800104cc  jmp     short loc_1800104D3
0x1800104ce  jbe     short loc_1800104DA
0x1800104d0  lea     edx, [rax-1]
0x1800104d3  cmp     r8d, edx
0x1800104d6  jbe     short loc_1800104BC
0x1800104d8  jmp     short loc_1800104E9
0x1800104da  lock dec dword ptr [r10+rax*8+4]
0x1800104e0  jmp     short loc_1800104E9
0x1800104e2  mov     dword ptr [r15], 0
0x1800104e9  mov     rdx, r14
0x1800104ec  mov     rcx, rbx; Context
0x1800104ef  call    RemoveRouteNode
0x1800104f4  mov     edi, eax
0x1800104f6  jmp     short loc_1800104FD
0x1800104f8  mov     edi, 103h
0x1800104fd  mov     rdx, [rsp+68h+var_38]
0x180010502  mov     rcx, rbx
0x180010505  call    LeaveSyncList
0x18001050a  lock dec dword ptr [rbx+8]
0x18001050e  mov     eax, edi
0x180010510  jmp     short loc_180010522
0x180010512  lock dec dword ptr [rbx+8]
0x180010516  mov     eax, 6
0x18001051b  jmp     short loc_180010522
0x18001051d  mov     eax, 6
0x180010522  lea     r11, [rsp+68h+var_28]
0x180010527  mov     rbx, [r11+38h]
0x18001052b  mov     rsi, [r11+40h]
0x18001052f  mov     rsp, r11
0x180010532  pop     r15
0x180010534  pop     r14
0x180010536  pop     r13
0x180010538  pop     r12
0x18001053a  pop     rdi
0x18001053b  retn
0x18001fd1e  push    rbp
0x18001fd20  sub     rsp, 30h
0x18001fd24  mov     rbp, rdx
0x18001fd27  mov     rax, [rcx]
0x18001fd2a  xor     ecx, ecx
0x18001fd2c  cmp     dword ptr [rax], 0C0000005h
0x18001fd32  setz    cl
0x18001fd35  mov     eax, ecx
0x18001fd37  add     rsp, 30h
0x18001fd3b  pop     rbp
0x18001fd3c  retn
```
