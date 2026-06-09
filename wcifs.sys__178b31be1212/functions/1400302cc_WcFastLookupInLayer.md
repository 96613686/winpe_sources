# WcFastLookupInLayer

- ea: `0x1400302cc`
- end: `0x14003042f`
- name: `WcFastLookupInLayer`
- size: `355`
- prototype: `__int64 __fastcall(struct _FLT_INSTANCE *, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140026260`

## callees

- `0x140007c60`
- `0x14002ac50`
- `0x14002f670`
- `0x1400302cc`

## import_xrefs

- `FLTMGR!FltQueryDirectoryFileEx` at `0x1400303d1`
- `FLTMGR!FltQueryDirectoryFileEx` at `0x1400303d1`
- `FLTMGR!FltReleaseContext` at `0x140030406`
- `FLTMGR!FltReleaseContext` at `0x140030406`
- `FLTMGR!FltGetInstanceContext` at `0x14003031b`
- `FLTMGR!FltGetInstanceContext` at `0x14003031b`

## pseudocode

```c
__int64 __fastcall WcFastLookupInLayer(struct _FLT_INSTANCE *a1, __int64 a2, __int64 a3, char a4)
{
  NTSTATUS InstanceContext; // ebx
  __int64 v8; // rsi
  int v9; // eax
  int v10; // eax
  PFLT_CONTEXT Context; // [rsp+40h] [rbp-40h] BYREF
  __int64 v13; // [rsp+48h] [rbp-38h] BYREF
  __int64 v14; // [rsp+50h] [rbp-30h] BYREF
  __int128 v15; // [rsp+58h] [rbp-28h] BYREF
  __int128 v16; // [rsp+68h] [rbp-18h] BYREF

  Context = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  InstanceContext = FltGetInstanceContext(a1, &Context);
  if ( !*((_QWORD *)Context + 7) )
    goto LABEL_12;
  LOWORD(v15) = *(_WORD *)(a2 + 24);
  WORD1(v15) = v15;
  *((_QWORD *)&v15 + 1) = a2 + 26;
  InstanceContext = WcLookupLayer(*((_QWORD *)Context + 7), *((_QWORD *)Context + 7) + 168LL, a2 + 8, &v13);
  if ( InstanceContext < 0 )
  {
LABEL_11:
    InstanceContext = a4 != 0 ? -1073741772 : -1073741766;
    goto LABEL_12;
  }
  v8 = v13;
  if ( (*(_DWORD *)(v13 + 16) & 0x24) != 0 )
    goto LABEL_12;
  v9 = WcLookupDirectoryTableEntry(v13, &v15, &v14);
  if ( v9 >= 0 )
  {
    v10 = FltQueryDirectoryFileEx(*(_QWORD *)(v8 + 40), *(_QWORD *)(v14 + 16), &v16, 16, 12, 19, a3, 0);
    if ( v10 != -1073741809 && v10 != -2147483642 )
    {
      InstanceContext = 0;
      goto LABEL_12;
    }
    goto LABEL_11;
  }
  InstanceContext = 0;
  if ( v9 != -1073741766 )
    InstanceContext = v9;
LABEL_12:
  if ( Context )
    FltReleaseContext(Context);
  return (unsigned int)InstanceContext;
}

```

## disassembly

```asm
0x1400302cc  push    rbp
0x1400302ce  push    rbx
0x1400302cf  push    rsi
0x1400302d0  push    rdi
0x1400302d1  push    r14
0x1400302d3  mov     rbp, rsp
0x1400302d6  sub     rsp, 80h
0x1400302dd  mov     rax, cs:__security_cookie
0x1400302e4  xor     rax, rsp
0x1400302e7  mov     [rbp+var_8], rax
0x1400302eb  xorps   xmm0, xmm0
0x1400302ee  mov     [rbp+Context], 0
0x1400302f6  mov     rsi, rdx
0x1400302f9  mov     [rbp+var_38], 0
0x140030301  lea     rdx, [rbp+Context]; Context
0x140030305  mov     [rbp+var_30], 0
0x14003030d  movups  [rbp+var_28], xmm0
0x140030311  mov     dil, r9b
0x140030314  mov     r14, r8
0x140030317  movups  [rbp+var_18], xmm0
0x14003031b  call    cs:__imp_FltGetInstanceContext
0x140030322  nop     dword ptr [rax+rax+00h]
0x140030327  mov     rcx, [rbp+Context]
0x14003032b  mov     ebx, eax
0x14003032d  cmp     qword ptr [rcx+38h], 0
0x140030332  jz      loc_1400303FD
0x140030338  movzx   eax, word ptr [rsi+18h]
0x14003033c  lea     r8, [rsi+8]
0x140030340  mov     word ptr [rbp+var_28], ax
0x140030344  lea     r9, [rbp+var_38]
0x140030348  mov     word ptr [rbp+var_28+2], ax
0x14003034c  lea     rax, [rsi+1Ah]
0x140030350  mov     qword ptr [rbp+var_28+8], rax
0x140030354  mov     rcx, [rcx+38h]
0x140030358  lea     rdx, [rcx+0A8h]
0x14003035f  call    WcLookupLayer
0x140030364  mov     ebx, eax
0x140030366  test    eax, eax
0x140030368  js      loc_1400303EF
0x14003036e  mov     rsi, [rbp+var_38]
0x140030372  mov     eax, [rsi+10h]
0x140030375  test    al, 24h
0x140030377  jnz     loc_1400303FD
0x14003037d  lea     r8, [rbp+var_30]
0x140030381  mov     rcx, rsi
0x140030384  lea     rdx, [rbp+var_28]
0x140030388  call    WcLookupDirectoryTableEntry
0x14003038d  test    eax, eax
0x14003038f  jns     short loc_14003039D
0x140030391  xor     ebx, ebx
0x140030393  cmp     eax, 0C000003Ah
0x140030398  cmovnz  ebx, eax
0x14003039b  jmp     short loc_1400303FD
0x14003039d  mov     rdx, [rbp+var_30]
0x1400303a1  lea     r8, [rbp+var_18]
0x1400303a5  mov     rcx, [rsi+28h]
0x1400303a9  mov     r9d, 10h
0x1400303af  mov     [rsp+80h+var_48], 0
0x1400303b8  mov     [rsp+80h+var_50], r14
0x1400303bd  mov     rdx, [rdx+10h]
0x1400303c1  mov     [rsp+80h+var_58], 13h
0x1400303c9  mov     [rsp+80h+var_60], 0Ch
0x1400303d1  call    cs:__imp_FltQueryDirectoryFileEx
0x1400303d8  nop     dword ptr [rax+rax+00h]
0x1400303dd  cmp     eax, 0C000000Fh
0x1400303e2  jz      short loc_1400303EF
0x1400303e4  cmp     eax, 80000006h
0x1400303e9  jz      short loc_1400303EF
0x1400303eb  xor     ebx, ebx
0x1400303ed  jmp     short loc_1400303FD
0x1400303ef  neg     dil
0x1400303f2  sbb     ebx, ebx
0x1400303f4  and     ebx, 0FFFFFFFAh
0x1400303f7  add     ebx, 0C000003Ah
0x1400303fd  mov     rcx, [rbp+Context]; Context
0x140030401  test    rcx, rcx
0x140030404  jz      short loc_140030412
0x140030406  call    cs:__imp_FltReleaseContext
0x14003040d  nop     dword ptr [rax+rax+00h]
0x140030412  mov     eax, ebx
0x140030414  mov     rcx, [rbp+var_8]
0x140030418  xor     rcx, rsp; StackCookie
0x14003041b  call    __security_check_cookie
0x140030420  add     rsp, 80h
0x140030427  pop     r14
0x140030429  pop     rdi
0x14003042a  pop     rsi
0x14003042b  pop     rbx
0x14003042c  pop     rbp
0x14003042d  retn
```
