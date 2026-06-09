# UdfCreateNewFile

- ea: `0x140031144`
- end: `0x1400312b7`
- name: `UdfCreateNewFile`
- size: `371`
- prototype: `__int64 __fastcall(int, int, int, __int64, char, char, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140042c40`

## callees

- `0x140004514`
- `0x14000cad4`
- `0x140013600`
- `0x140017ecc`
- `0x140030818`
- `0x140031144`
- `0x140041de0`

## pseudocode

```c
__int64 __fastcall UdfCreateNewFile(__int64 a1, __int64 a2, _QWORD *a3, unsigned __int16 *a4, char a5, char a6, int a7)
{
  __int64 v11; // r8
  __int64 v13; // rdx
  __int64 v14; // r8
  char v15; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v16[7]; // [rsp+51h] [rbp-47h] BYREF
  _QWORD v17[8]; // [rsp+58h] [rbp-40h] BYREF

  v15 = 0;
  v17[0] = 0;
  *(_DWORD *)&v16[3] = 0;
  if ( !(unsigned __int8)UdfUnicodeLengthAsCS0Dstring(a1, a4, v16, &v15) )
    return 3221225523LL;
  if ( a5 )
  {
    if ( *(_WORD *)(a2 + 500) == 0xFFFF )
    {
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 26, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids);
      }
      return 3221226218LL;
    }
    if ( (a7 & 0x100) != 0 )
      return 3221225485LL;
  }
  LOBYTE(v11) = 5 - (a5 != 0);
  UdfCreateNewIcb(a1, a2, v11, a6, (unsigned int *)&v16[3], v17, a7);
  UdfCreateLink(a1, a2, 0, *(int *)&v16[3], v17[0], a5, (a7 & 2) != 0, a4, a3, v15);
  if ( (*(_DWORD *)(a2 + 212) & 8) == 0 )
  {
    LOBYTE(v13) = a5;
    UdfUpdateLvidCounts(a1, v13, 1);
  }
  v14 = *(_DWORD *)(a2 + 212) >> 23;
  LOBYTE(v14) = (*(_DWORD *)(a2 + 212) & 0x800000) != 0;
  UdfUpdateDirNames(a1, (__int64)a3, v14, a6);
  return 0;
}

```

## disassembly

```asm
0x140031144  mov     rax, rsp
0x140031147  push    rbx
0x140031148  push    rbp
0x140031149  push    rsi
0x14003114a  push    rdi
0x14003114b  push    r14
0x14003114d  push    r15
0x14003114f  sub     rsp, 68h
0x140031153  mov     r15, r9
0x140031156  mov     byte ptr [rax-48h], 0
0x14003115a  mov     r14, r8
0x14003115d  mov     qword ptr [rax-40h], 0
0x140031165  mov     rsi, rdx
0x140031168  mov     dword ptr [rax-44h], 0
0x14003116f  mov     rdx, r15
0x140031172  lea     r9, [rax-48h]
0x140031176  lea     r8, [rax-47h]
0x14003117a  mov     rbp, rcx
0x14003117d  call    UdfUnicodeLengthAsCS0Dstring
0x140031182  test    al, al
0x140031184  jnz     short loc_140031190
0x140031186  mov     eax, 0C0000033h
0x14003118b  jmp     loc_1400312A9
0x140031190  mov     bl, [rsp+98h+arg_20]
0x140031197  mov     edi, [rsp+98h+arg_30]
0x14003119e  test    bl, bl
0x1400311a0  jz      short loc_1400311F9
0x1400311a2  mov     eax, 0FFFFh
0x1400311a7  cmp     [rsi+1F4h], ax
0x1400311ae  jnz     short loc_1400311E9
0x1400311b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400311b7  lea     rax, WPP_GLOBAL_Control
0x1400311be  cmp     rcx, rax
0x1400311c1  jz      short loc_1400311DF
0x1400311c3  mov     eax, [rcx+2Ch]
0x1400311c6  test    al, 10h
0x1400311c8  jz      short loc_1400311DF
0x1400311ca  mov     rcx, [rcx+18h]
0x1400311ce  lea     r8, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids
0x1400311d5  mov     edx, 1Ah
0x1400311da  call    WPP_SF_
0x1400311df  mov     eax, 0C00002EAh
0x1400311e4  jmp     loc_1400312A9
0x1400311e9  bt      edi, 8
0x1400311ed  jnb     short loc_1400311F9
0x1400311ef  mov     eax, 0C000000Dh
0x1400311f4  jmp     loc_1400312A9
0x1400311f9  mov     r9b, [rsp+98h+arg_28]
0x140031201  mov     al, bl
0x140031203  neg     al
0x140031205  mov     dword ptr [rsp+98h+var_68], edi
0x140031209  lea     rax, [rsp+98h+var_40]
0x14003120e  mov     rdx, rsi
0x140031211  mov     qword ptr [rsp+98h+var_70], rax
0x140031216  sbb     r8b, r8b
0x140031219  lea     rax, [rsp+98h+var_44]
0x14003121e  add     r8b, 5
0x140031222  mov     rcx, rbp
0x140031225  mov     qword ptr [rsp+98h+var_78], rax
0x14003122a  call    UdfCreateNewIcb
0x14003122f  mov     al, [rsp+98h+var_48]
0x140031233  xor     r8d, r8d
0x140031236  mov     r9d, [rsp+98h+var_44]
0x14003123b  mov     rdx, rsi; int
0x14003123e  mov     [rsp+98h+var_50], al; char
0x140031242  mov     rcx, rbp; int
0x140031245  mov     eax, dword ptr [rsp+98h+var_40]
0x140031249  mov     qword ptr [rsp+98h+var_58], r14; int
0x14003124e  mov     [rsp+98h+var_60], r15; __int64
0x140031253  shr     edi, 1
0x140031255  and     dil, 1
0x140031259  mov     [rsp+98h+var_68], dil; char
0x14003125e  mov     [rsp+98h+var_70], bl; char
0x140031262  mov     [rsp+98h+var_78], eax; int
0x140031266  call    UdfCreateLink
0x14003126b  mov     eax, [rsi+0D4h]
0x140031271  test    al, 8
0x140031273  jnz     short loc_140031285
0x140031275  mov     r8d, 1
0x14003127b  mov     dl, bl
0x14003127d  mov     rcx, rbp
0x140031280  call    UdfUpdateLvidCounts
0x140031285  mov     r8d, [rsi+0D4h]
0x14003128c  mov     rdx, r14
0x14003128f  mov     r9b, [rsp+98h+arg_28]
0x140031297  mov     rcx, rbp
0x14003129a  shr     r8d, 17h
0x14003129e  and     r8b, 1
0x1400312a2  call    UdfUpdateDirNames
0x1400312a7  xor     eax, eax
0x1400312a9  add     rsp, 68h
0x1400312ad  pop     r15
0x1400312af  pop     r14
0x1400312b1  pop     rdi
0x1400312b2  pop     rsi
0x1400312b3  pop     rbp
0x1400312b4  pop     rbx
0x1400312b5  retn
```
