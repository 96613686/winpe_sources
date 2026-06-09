# CtxtCreateLogSess

- ea: `0x18001b2f8`
- end: `0x18001b4a8`
- name: `CtxtCreateLogSess`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18001e4b0`

## callees

- `0x180003520`
- `0x1800061a0`
- `0x18000bc00`
- `0x18000d980`
- `0x180011fec`
- `0x1800185b8`
- `0x180018b18`
- `0x1800192a8`
- `0x18001b2f8`
- `0x1800226cc`

## pseudocode

```c
__int64 __fastcall CtxtCreateLogSess(__int64 a1)
{
  __int64 Memory; // rax
  __int64 v3; // rdi
  unsigned int v4; // ebx
  PVOID *v5; // rcx
  int v6; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 175, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids);
  Memory = DigestAllocateMemory(0x80u);
  v3 = Memory;
  if ( Memory )
  {
    LogonSessionInit(Memory);
    *(_DWORD *)(v3 + 44) = 3;
    *(_QWORD *)(v3 + 32) = *(_QWORD *)(a1 + 552);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        177,
        &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids,
        *(unsigned int *)(a1 + 556),
        *(_DWORD *)(a1 + 552));
    v6 = UnicodeStringDuplicate(v3 + 48, a1 + 600);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v6 = UnicodeStringDuplicate(v3 + 64, a1 + 568);
      v4 = v6;
      if ( v6 >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v3);
        LogSessHandlerInsert(v3);
        goto LABEL_25;
      }
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v8 = 179;
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_20;
      v8 = 178;
    }
    WPP_SF_d(v7[2], v8, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, (unsigned int)v6);
LABEL_20:
    LogonSessionFree((HLOCAL)v3);
    goto LABEL_25;
  }
  v4 = -2146893056;
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, 2148074240LL);
LABEL_25:
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && *((char *)v5 + 28) < 0 )
    WPP_SF_d(v5[2], 181, &WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18001b2f8  push    rbx
0x18001b2fa  push    rbp
0x18001b2fb  push    rsi
0x18001b2fc  push    rdi
0x18001b2fd  push    r14
0x18001b2ff  sub     rsp, 30h
0x18001b303  mov     rsi, rcx
0x18001b306  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b30d  lea     rbp, WPP_GLOBAL_Control
0x18001b314  lea     r14, WPP_0ed1b0878c133b2013fdb6f803dbb21a_Traceguids
0x18001b31b  cmp     rcx, rbp
0x18001b31e  jz      short loc_18001B337
0x18001b320  test    byte ptr [rcx+1Ch], 80h
0x18001b324  jz      short loc_18001B337
0x18001b326  mov     rcx, [rcx+10h]
0x18001b32a  mov     edx, 0AFh
0x18001b32f  mov     r8, r14
0x18001b332  call    WPP_SF_
0x18001b337  mov     ecx, 80h; Size
0x18001b33c  call    DigestAllocateMemory
0x18001b341  mov     rdi, rax
0x18001b344  test    rax, rax
0x18001b347  jnz     short loc_18001B384
0x18001b349  mov     ebx, 80090300h
0x18001b34e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b355  cmp     rcx, rbp
0x18001b358  jz      loc_18001B49B
0x18001b35e  test    byte ptr [rcx+1Ch], 1
0x18001b362  jz      loc_18001B47C
0x18001b368  mov     rcx, [rcx+10h]
0x18001b36c  mov     edx, 0B0h
0x18001b371  mov     r9d, 80090300h
0x18001b377  mov     r8, r14
0x18001b37a  call    WPP_SF_d
0x18001b37f  jmp     loc_18001B475
0x18001b384  mov     rcx, rdi
0x18001b387  call    LogonSessionInit
0x18001b38c  mov     dword ptr [rdi+2Ch], 3
0x18001b393  mov     rax, [rsi+228h]
0x18001b39a  mov     [rdi+20h], rax
0x18001b39e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3a5  cmp     rcx, rbp
0x18001b3a8  jz      short loc_18001B3D2
0x18001b3aa  test    byte ptr [rcx+1Ch], 4
0x18001b3ae  jz      short loc_18001B3D2
0x18001b3b0  mov     eax, [rsi+228h]
0x18001b3b6  mov     edx, 0B1h
0x18001b3bb  mov     r9d, [rsi+22Ch]
0x18001b3c2  mov     r8, r14
0x18001b3c5  mov     rcx, [rcx+10h]
0x18001b3c9  mov     [rsp+58h+var_38], eax
0x18001b3cd  call    WPP_SF_dd
0x18001b3d2  lea     rdx, [rsi+258h]
0x18001b3d9  lea     rcx, [rdi+30h]
0x18001b3dd  call    UnicodeStringDuplicate
0x18001b3e2  mov     ebx, eax
0x18001b3e4  test    eax, eax
0x18001b3e6  jns     short loc_18001B401
0x18001b3e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b3ef  cmp     rcx, rbp
0x18001b3f2  jz      short loc_18001B43D
0x18001b3f4  test    byte ptr [rcx+1Ch], 1
0x18001b3f8  jz      short loc_18001B43D
0x18001b3fa  mov     edx, 0B2h
0x18001b3ff  jmp     short loc_18001B42E
0x18001b401  lea     rdx, [rsi+238h]
0x18001b408  lea     rcx, [rdi+40h]
0x18001b40c  call    UnicodeStringDuplicate
0x18001b411  mov     ebx, eax
0x18001b413  test    eax, eax
0x18001b415  jns     short loc_18001B447
0x18001b417  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b41e  cmp     rcx, rbp
0x18001b421  jz      short loc_18001B43D
0x18001b423  test    byte ptr [rcx+1Ch], 1
0x18001b427  jz      short loc_18001B43D
0x18001b429  mov     edx, 0B3h
0x18001b42e  mov     rcx, [rcx+10h]
0x18001b432  mov     r9d, eax
0x18001b435  mov     r8, r14
0x18001b438  call    WPP_SF_d
0x18001b43d  mov     rcx, rdi; hMem
0x18001b440  call    LogonSessionFree
0x18001b445  jmp     short loc_18001B475
0x18001b447  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b44e  cmp     rcx, rbp
0x18001b451  jz      short loc_18001B46D
0x18001b453  test    byte ptr [rcx+1Ch], 4
0x18001b457  jz      short loc_18001B46D
0x18001b459  mov     rcx, [rcx+10h]
0x18001b45d  mov     edx, 0B4h
0x18001b462  mov     r9, rdi
0x18001b465  mov     r8, r14
0x18001b468  call    WPP_SF_q
0x18001b46d  mov     rcx, rdi
0x18001b470  call    LogSessHandlerInsert
0x18001b475  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b47c  cmp     rcx, rbp
0x18001b47f  jz      short loc_18001B49B
0x18001b481  test    byte ptr [rcx+1Ch], 80h
0x18001b485  jz      short loc_18001B49B
0x18001b487  mov     rcx, [rcx+10h]
0x18001b48b  mov     edx, 0B5h
0x18001b490  mov     r9d, ebx
0x18001b493  mov     r8, r14
0x18001b496  call    WPP_SF_d
0x18001b49b  mov     eax, ebx
0x18001b49d  add     rsp, 30h
0x18001b4a1  pop     r14
0x18001b4a3  pop     rdi
0x18001b4a4  pop     rsi
0x18001b4a5  pop     rbp
0x18001b4a6  pop     rbx
0x18001b4a7  retn
```
