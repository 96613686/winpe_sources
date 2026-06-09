# WcFastLookupInLayer

- ea: `0x14003027c`
- end: `0x1400303df`
- name: `WcFastLookupInLayer`
- size: `355`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140026210`

## callees

- `0x140007c60`
- `0x14002ac00`
- `0x14002f620`
- `0x14003027c`

## import_xrefs

- `FLTMGR!FltQueryDirectoryFileEx` at `0x140030381`
- `FLTMGR!FltQueryDirectoryFileEx` at `0x140030381`
- `FLTMGR!FltReleaseContext` at `0x1400303b6`
- `FLTMGR!FltReleaseContext` at `0x1400303b6`
- `FLTMGR!FltGetInstanceContext` at `0x1400302cb`
- `FLTMGR!FltGetInstanceContext` at `0x1400302cb`

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
0x14003027c  push    rbp
0x14003027e  push    rbx
0x14003027f  push    rsi
0x140030280  push    rdi
0x140030281  push    r14
0x140030283  mov     rbp, rsp
0x140030286  sub     rsp, 80h
0x14003028d  mov     rax, cs:__security_cookie
0x140030294  xor     rax, rsp
0x140030297  mov     [rbp+var_8], rax
0x14003029b  xorps   xmm0, xmm0
0x14003029e  mov     [rbp+Context], 0
0x1400302a6  mov     rsi, rdx
0x1400302a9  mov     [rbp+var_38], 0
0x1400302b1  lea     rdx, [rbp+Context]; Context
0x1400302b5  mov     [rbp+var_30], 0
0x1400302bd  movups  [rbp+var_28], xmm0
0x1400302c1  mov     dil, r9b
0x1400302c4  mov     r14, r8
0x1400302c7  movups  [rbp+var_18], xmm0
0x1400302cb  call    cs:__imp_FltGetInstanceContext
0x1400302d2  nop     dword ptr [rax+rax+00h]
0x1400302d7  mov     rcx, [rbp+Context]
0x1400302db  mov     ebx, eax
0x1400302dd  cmp     qword ptr [rcx+38h], 0
0x1400302e2  jz      loc_1400303AD
0x1400302e8  movzx   eax, word ptr [rsi+18h]
0x1400302ec  lea     r8, [rsi+8]
0x1400302f0  mov     word ptr [rbp+var_28], ax
0x1400302f4  lea     r9, [rbp+var_38]
0x1400302f8  mov     word ptr [rbp+var_28+2], ax
0x1400302fc  lea     rax, [rsi+1Ah]
0x140030300  mov     qword ptr [rbp+var_28+8], rax
0x140030304  mov     rcx, [rcx+38h]
0x140030308  lea     rdx, [rcx+0A8h]
0x14003030f  call    WcLookupLayer
0x140030314  mov     ebx, eax
0x140030316  test    eax, eax
0x140030318  js      loc_14003039F
0x14003031e  mov     rsi, [rbp+var_38]
0x140030322  mov     eax, [rsi+10h]
0x140030325  test    al, 24h
0x140030327  jnz     loc_1400303AD
0x14003032d  lea     r8, [rbp+var_30]
0x140030331  mov     rcx, rsi
0x140030334  lea     rdx, [rbp+var_28]
0x140030338  call    WcLookupDirectoryTableEntry
0x14003033d  test    eax, eax
0x14003033f  jns     short loc_14003034D
0x140030341  xor     ebx, ebx
0x140030343  cmp     eax, 0C000003Ah
0x140030348  cmovnz  ebx, eax
0x14003034b  jmp     short loc_1400303AD
0x14003034d  mov     rdx, [rbp+var_30]
0x140030351  lea     r8, [rbp+var_18]
0x140030355  mov     rcx, [rsi+28h]
0x140030359  mov     r9d, 10h
0x14003035f  mov     [rsp+80h+var_48], 0
0x140030368  mov     [rsp+80h+var_50], r14
0x14003036d  mov     rdx, [rdx+10h]
0x140030371  mov     [rsp+80h+var_58], 13h
0x140030379  mov     [rsp+80h+var_60], 0Ch
0x140030381  call    cs:__imp_FltQueryDirectoryFileEx
0x140030388  nop     dword ptr [rax+rax+00h]
0x14003038d  cmp     eax, 0C000000Fh
0x140030392  jz      short loc_14003039F
0x140030394  cmp     eax, 80000006h
0x140030399  jz      short loc_14003039F
0x14003039b  xor     ebx, ebx
0x14003039d  jmp     short loc_1400303AD
0x14003039f  neg     dil
0x1400303a2  sbb     ebx, ebx
0x1400303a4  and     ebx, 0FFFFFFFAh
0x1400303a7  add     ebx, 0C000003Ah
0x1400303ad  mov     rcx, [rbp+Context]; Context
0x1400303b1  test    rcx, rcx
0x1400303b4  jz      short loc_1400303C2
0x1400303b6  call    cs:__imp_FltReleaseContext
0x1400303bd  nop     dword ptr [rax+rax+00h]
0x1400303c2  mov     eax, ebx
0x1400303c4  mov     rcx, [rbp+var_8]
0x1400303c8  xor     rcx, rsp; StackCookie
0x1400303cb  call    __security_check_cookie
0x1400303d0  add     rsp, 80h
0x1400303d7  pop     r14
0x1400303d9  pop     rdi
0x1400303da  pop     rsi
0x1400303db  pop     rbx
0x1400303dc  pop     rbp
0x1400303dd  retn
```
