# SkhalConfigureSecureAtsDevice

- ea: `0x1400891fc`
- end: `0x140089386`
- name: `SkhalConfigureSecureAtsDevice`
- size: `394`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140014dd0`

## callees

- `0x140008080`
- `0x1400337d4`
- `0x1400891fc`
- `0x14008938c`
- `0x14008b420`
- `0x14008c054`
- `0x1400f3620`

## pseudocode

```c
__int64 __fastcall SkhalConfigureSecureAtsDevice(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rdx
  _DWORD *v6; // rcx
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v10; // edi
  int v11; // ebx
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 FunctionInTree; // rax
  unsigned int v16; // r11d
  __int64 v17; // rdx
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  unsigned __int8 v20[8]; // [rsp+40h] [rbp-48h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-40h] BYREF
  int v22; // [rsp+58h] [rbp-30h]
  int v23; // [rsp+5Ch] [rbp-2Ch]

  v20[0] = KeGetCurrentIrql();
  if ( !(unsigned __int8)SkhalPciEnabled(a1, a2, a3, a4) )
    return 3221225659LL;
  if ( *v6 == 2 )
  {
    v9 = (unsigned int)v6[1];
    if ( (unsigned int)v9 >= 0xFFFF || *(_BYTE *)(a1 + 9) >= 0x20u || *(_BYTE *)(a1 + 10) >= 8u )
    {
      return (unsigned int)-1073741810;
    }
    else
    {
      if ( *(_BYTE *)v5 )
      {
        v10 = 26;
        v11 = 32 * (*(_DWORD *)(v5 + 4) & 0x1F);
      }
      else
      {
        v11 = 0;
        v10 = 17;
      }
      SkhalpPciAcquireSegmentFunctionTreeLock(v9, v20);
      LOBYTE(v12) = *(_BYTE *)(a1 + 10);
      LOBYTE(v13) = *(_BYTE *)(a1 + 9);
      LOBYTE(v14) = *(_BYTE *)(a1 + 8);
      FunctionInTree = SkhalpPciFindFunctionInTree(*(unsigned int *)(a1 + 4), v14, v13, v12);
      v17 = FunctionInTree;
      if ( FunctionInTree && (*(_DWORD *)(FunctionInTree + 40) & 1) != 0 )
      {
        if ( *(_WORD *)(FunctionInTree + 364) )
        {
          v18 = *(_QWORD *)(FunctionInTree + 32);
          if ( *(_DWORD *)(v18 + 140) == 1 )
          {
            v19 = *(_QWORD *)(v18 + 176);
            if ( v19 != -1 && !*(_DWORD *)(v18 + 184) )
            {
              LOBYTE(v17) = v20[0];
              SkhalpPciReleaseSegmentFunctionTreeLock(v16, v17);
              if ( v19 <= 0x3FFFFFFFFFFFFFFFLL )
              {
                v21[1] = v19;
                v21[0] = -1;
                v22 = v10;
                v23 = v11;
                return (unsigned int)ShvlpInitiateFastHypercall(256, (unsigned int)v21, 24, 0, 0, 0, 0);
              }
              else
              {
                return (unsigned int)-1073741811;
              }
            }
          }
        }
        v8 = -1073741436;
      }
      else
      {
        v8 = -1073741810;
      }
      LOBYTE(v17) = v20[0];
      SkhalpPciReleaseSegmentFunctionTreeLock(v16, v17);
    }
  }
  else
  {
    return (unsigned int)-1073741637;
  }
  return v8;
}

```

## disassembly

```asm
0x1400891fc  mov     [rsp+arg_10], rbx
0x140089201  push    rbp
0x140089202  push    rsi
0x140089203  push    rdi
0x140089204  sub     rsp, 70h
0x140089208  mov     rax, cs:__security_cookie
0x14008920f  xor     rax, rsp
0x140089212  mov     [rsp+88h+var_28], rax
0x140089217  mov     rsi, rcx
0x14008921a  mov     rax, cr8
0x14008921e  mov     [rsp+88h+var_48], al
0x140089222  call    SkhalPciEnabled
0x140089227  xor     ebp, ebp
0x140089229  test    al, al
0x14008922b  jnz     short loc_140089237
0x14008922d  mov     eax, 0C00000BBh
0x140089232  jmp     loc_140089368
0x140089237  cmp     dword ptr [rcx], 2
0x14008923a  jz      short loc_140089246
0x14008923c  mov     ebx, 0C00000BBh
0x140089241  jmp     loc_140089366
0x140089246  mov     ecx, [rcx+4]
0x140089249  cmp     ecx, 0FFFFh
0x14008924f  jnb     loc_140089361
0x140089255  cmp     byte ptr [rsi+9], 20h ; ' '
0x140089259  jnb     loc_140089361
0x14008925f  cmp     byte ptr [rsi+0Ah], 8
0x140089263  jnb     loc_140089361
0x140089269  cmp     [rdx], bpl
0x14008926c  jz      short loc_14008927E
0x14008926e  mov     ebx, [rdx+4]
0x140089271  mov     edi, 1Ah
0x140089276  and     ebx, 1Fh
0x140089279  shl     ebx, 5
0x14008927c  jmp     short loc_140089285
0x14008927e  mov     ebx, ebp
0x140089280  mov     edi, 11h
0x140089285  lea     rdx, [rsp+88h+var_48]
0x14008928a  call    SkhalpPciAcquireSegmentFunctionTreeLock
0x14008928f  mov     r11d, [rsi+4]
0x140089293  mov     ecx, r11d
0x140089296  mov     r9b, [rsi+0Ah]
0x14008929a  mov     r8b, [rsi+9]
0x14008929e  mov     dl, [rsi+8]
0x1400892a1  call    SkhalpPciFindFunctionInTree
0x1400892a6  mov     rdx, rax
0x1400892a9  test    rax, rax
0x1400892ac  jnz     short loc_1400892B8
0x1400892ae  mov     ebx, 0C000000Eh
0x1400892b3  jmp     loc_140089353
0x1400892b8  mov     eax, [rax+28h]
0x1400892bb  test    al, 1
0x1400892bd  jz      short loc_1400892AE
0x1400892bf  cmp     [rdx+16Ch], bp
0x1400892c6  jz      loc_14008934E
0x1400892cc  mov     rax, [rdx+20h]
0x1400892d0  cmp     dword ptr [rax+8Ch], 1
0x1400892d7  jnz     short loc_14008934E
0x1400892d9  mov     rsi, [rax+0B0h]
0x1400892e0  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1400892e4  jz      short loc_14008934E
0x1400892e6  cmp     [rax+0B8h], ebp
0x1400892ec  jnz     short loc_14008934E
0x1400892ee  mov     dl, [rsp+88h+var_48]
0x1400892f2  mov     ecx, r11d
0x1400892f5  call    SkhalpPciReleaseSegmentFunctionTreeLock
0x1400892fa  mov     rax, 3FFFFFFFFFFFFFFFh
0x140089304  cmp     rsi, rax
0x140089307  jbe     short loc_140089310
0x140089309  mov     ebx, 0C000000Dh
0x14008930e  jmp     short loc_140089366
0x140089310  xor     r9d, r9d
0x140089313  mov     [rsp+88h+var_58], ebp
0x140089317  mov     [rsp+88h+var_60], rbp
0x14008931c  lea     rdx, [rsp+88h+var_40]
0x140089321  mov     ecx, 100h
0x140089326  mov     [rsp+88h+var_38], rsi
0x14008932b  mov     [rsp+88h+var_40], 0FFFFFFFFFFFFFFFFh
0x140089334  lea     r8d, [r9+18h]
0x140089338  mov     [rsp+88h+var_30], edi
0x14008933c  mov     [rsp+88h+var_2C], ebx
0x140089340  mov     [rsp+88h+var_68], rbp
0x140089345  call    ShvlpInitiateFastHypercall
0x14008934a  mov     ebx, eax
0x14008934c  jmp     short loc_140089366
0x14008934e  mov     ebx, 0C0000184h
0x140089353  mov     dl, [rsp+88h+var_48]
0x140089357  mov     ecx, r11d
0x14008935a  call    SkhalpPciReleaseSegmentFunctionTreeLock
0x14008935f  jmp     short loc_140089366
0x140089361  mov     ebx, 0C000000Eh
0x140089366  mov     eax, ebx
0x140089368  mov     rcx, [rsp+88h+var_28]
0x14008936d  xor     rcx, rsp; StackCookie
0x140089370  call    __security_check_cookie
0x140089375  mov     rbx, [rsp+88h+arg_10]
0x14008937d  add     rsp, 70h
0x140089381  pop     rdi
0x140089382  pop     rsi
0x140089383  pop     rbp
0x140089384  retn
```
