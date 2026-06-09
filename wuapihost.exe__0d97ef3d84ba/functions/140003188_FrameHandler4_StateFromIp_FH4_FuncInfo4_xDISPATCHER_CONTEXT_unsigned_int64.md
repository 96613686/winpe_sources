# __FrameHandler4::StateFromIp(FH4::FuncInfo4 *,_xDISPATCHER_CONTEXT *,unsigned __int64)

- ea: `0x140003188`
- end: `0x140003275`
- name: `?StateFromIp@__FrameHandler4@@SAHPEAUFuncInfo4@FH4@@PEAU_xDISPATCHER_CONTEXT@@_K@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct FH4::FuncInfo4 *, struct _xDISPATCHER_CONTEXT *, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x140003178`
- `0x1400040e0`

## callees

- `0x140003188`

## pseudocode

```c
__int64 __fastcall __FrameHandler4::StateFromIp(
        struct FH4::FuncInfo4 *a1,
        struct _xDISPATCHER_CONTEXT *a2,
        unsigned __int64 a3)
{
  __int64 ImageBase; // rsi
  unsigned int v6; // edi
  _BYTE *v7; // r9
  unsigned int v8; // r8d
  unsigned int v9; // edx
  __int64 v10; // rcx
  _BYTE *v11; // r9
  unsigned int v12; // r11d
  __int64 BeginAddress; // r10
  __int64 v14; // rcx
  _BYTE *v15; // r9
  __int64 v16; // rcx

  if ( !*((_DWORD *)a1 + 4) )
    return 0xFFFFFFFFLL;
  ImageBase = a2->ImageBase;
  v6 = 0;
  v7 = (_BYTE *)(ImageBase + *((int *)a1 + 4));
  v8 = 0;
  v9 = -1;
  v10 = *v7 & 0xF;
  v11 = &v7[-*((char *)&FH4::s_negLengthTab + v10)];
  v12 = *((_DWORD *)v11 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v10);
  if ( !v12 )
    return 0xFFFFFFFFLL;
  BeginAddress = a2->FunctionEntry->BeginAddress;
  do
  {
    v14 = *v11 & 0xF;
    v15 = &v11[-*((char *)&FH4::s_negLengthTab + v14)];
    v6 += *((_DWORD *)v15 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v14);
    if ( a3 < ImageBase + BeginAddress + (unsigned __int64)v6 )
      break;
    ++v8;
    v16 = *v15 & 0xF;
    v11 = &v15[-*((char *)&FH4::s_negLengthTab + v16)];
    v9 = (*((_DWORD *)v11 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v16)) - 1;
  }
  while ( v8 < v12 );
  if ( !v8 )
    return (unsigned int)-1;
  return v9;
}

```

## disassembly

```asm
0x140003188  mov     rax, rsp
0x14000318b  mov     [rax+8], rbx
0x14000318f  mov     [rax+10h], rbp
0x140003193  mov     [rax+18h], rsi
0x140003197  mov     [rax+20h], rdi
0x14000319b  push    r14
0x14000319d  or      ebp, 0FFFFFFFFh
0x1400031a0  mov     rbx, r8
0x1400031a3  cmp     dword ptr [rcx+10h], 0
0x1400031a7  mov     r10, rdx
0x1400031aa  jz      loc_14000325C
0x1400031b0  movsxd  r9, dword ptr [rcx+10h]
0x1400031b4  lea     r14, cs:140000000h
0x1400031bb  mov     rsi, [rdx+8]
0x1400031bf  xor     edi, edi
0x1400031c1  add     r9, rsi
0x1400031c4  xor     r8d, r8d
0x1400031c7  mov     edx, ebp
0x1400031c9  movzx   ecx, byte ptr [r9]
0x1400031cd  and     ecx, 0Fh
0x1400031d0  movsx   rax, byte ptr [rcx+r14+7460h]
0x1400031d9  mov     cl, [rcx+r14+7470h]
0x1400031e1  sub     r9, rax
0x1400031e4  mov     r11d, [r9-4]
0x1400031e8  shr     r11d, cl
0x1400031eb  test    r11d, r11d
0x1400031ee  jz      short loc_14000325C
0x1400031f0  mov     rax, [r10+10h]
0x1400031f4  mov     r10d, [rax]
0x1400031f7  movzx   ecx, byte ptr [r9]
0x1400031fb  and     ecx, 0Fh
0x1400031fe  movsx   rax, byte ptr [rcx+r14+7460h]
0x140003207  mov     cl, [rcx+r14+7470h]
0x14000320f  sub     r9, rax
0x140003212  mov     eax, [r9-4]
0x140003216  shr     eax, cl
0x140003218  add     edi, eax
0x14000321a  mov     eax, edi
0x14000321c  add     rax, r10
0x14000321f  add     rax, rsi
0x140003222  cmp     rbx, rax
0x140003225  jb      short loc_140003252
0x140003227  movzx   ecx, byte ptr [r9]
0x14000322b  inc     r8d
0x14000322e  and     ecx, 0Fh
0x140003231  movsx   rax, byte ptr [rcx+r14+7460h]
0x14000323a  mov     cl, [rcx+r14+7470h]
0x140003242  sub     r9, rax
0x140003245  mov     edx, [r9-4]
0x140003249  shr     edx, cl
0x14000324b  dec     edx
0x14000324d  cmp     r8d, r11d
0x140003250  jb      short loc_1400031F7
0x140003252  test    r8d, r8d
0x140003255  cmovz   edx, ebp
0x140003258  mov     eax, edx
0x14000325a  jmp     short loc_14000325E
0x14000325c  mov     eax, ebp
0x14000325e  mov     rbx, [rsp+8+arg_0]
0x140003263  mov     rbp, [rsp+8+arg_8]
0x140003268  mov     rsi, [rsp+8+arg_10]
0x14000326d  mov     rdi, [rsp+8+arg_18]
0x140003272  pop     r14
0x140003274  retn
```
