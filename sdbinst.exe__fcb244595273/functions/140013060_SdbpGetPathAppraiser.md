# SdbpGetPathAppraiser

- ea: `0x140013060`
- end: `0x14001318e`
- name: `SdbpGetPathAppraiser`
- size: `302`
- prototype: `__int64 __fastcall(_WORD *, unsigned __int64, unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x14000f158`
- `0x14001008c`
- `0x1400100c4`
- `0x140013060`
- `0x14001357c`
- `0x14002e420`

## string_xrefs

- `0x140013102`: `AslPathCombine failed [%x]`
- `0x14001310f`: `SdbpGetPathAppraiser`

## pseudocode

```c
__int64 __fastcall SdbpGetPathAppraiser(_WORD *a1, unsigned __int64 a2, unsigned __int16 *a3, __int64 a4)
{
  unsigned __int16 *v5; // r10
  int ProcessHostGuestArchitectures; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  __int64 v12; // r8
  _WORD v13[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 v14; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v15[22]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v16[264]; // [rsp+50h] [rbp-B0h] BYREF

  v5 = a3;
  *(_OWORD *)v15 = *(_OWORD *)L"\\appraiser";
  *(_QWORD *)&v15[14] = *(_QWORD *)L"ser";
  if ( a2 < 0xB )
    return 3221225507LL;
  *a1 = 0;
  v16[0] = 0;
  v14 = -1;
  v13[0] = -1;
  if ( !a3 )
    v5 = (unsigned __int16 *)&Format;
  ProcessHostGuestArchitectures = AslPathCombine(v15, v5, v16, 260);
  v10 = ProcessHostGuestArchitectures;
  if ( ProcessHostGuestArchitectures >= 0 )
  {
    ProcessHostGuestArchitectures = SdbpGetProcessHostGuestArchitectures(&v14, v13, a4);
    v10 = ProcessHostGuestArchitectures;
    if ( ProcessHostGuestArchitectures >= 0 )
      return (unsigned int)AslEnvGetSysNativeDirPathForGuestBuf(a1, a2, v16, v14, v13);
    v11 = "SdbpGetProcessHostGuestArchitectures failed [%x]";
    v12 = 1309;
  }
  else
  {
    v11 = "AslPathCombine failed [%x]";
    v12 = 1303;
  }
  AslLogCallPrintf(1, "SdbpGetPathAppraiser", v12, v11, ProcessHostGuestArchitectures);
  return v10;
}

```

## disassembly

```asm
0x140013060  push    rbp
0x140013062  push    rbx
0x140013063  push    rsi
0x140013064  push    rdi
0x140013065  push    r14
0x140013067  lea     rbp, [rsp-170h]
0x14001306f  sub     rsp, 270h
0x140013076  mov     rax, cs:__security_cookie
0x14001307d  xor     rax, rsp
0x140013080  mov     [rbp+190h+var_30], rax
0x140013087  movsd   xmm1, qword ptr cs:aAppraiser+0Eh; "ser"
0x14001308f  mov     r14, r9
0x140013092  mov     r10, r8
0x140013095  mov     rdi, rdx
0x140013098  mov     rsi, rcx
0x14001309b  movups  xmm0, xmmword ptr cs:aAppraiser; "\\appraiser"
0x1400130a2  movups  xmmword ptr [rsp+290h+var_258], xmm0
0x1400130a7  movsd   qword ptr [rsp+290h+var_258+0Eh], xmm1
0x1400130ad  cmp     rdx, 0Bh
0x1400130b1  jnb     short loc_1400130BD
0x1400130b3  mov     eax, 0C0000023h
0x1400130b8  jmp     loc_140013171
0x1400130bd  xor     eax, eax
0x1400130bf  lea     r8, [rsp+290h+var_240]
0x1400130c4  mov     [rcx], ax
0x1400130c7  test    r10, r10
0x1400130ca  mov     [rsp+290h+var_240], ax
0x1400130cf  lea     rcx, [rsp+290h+var_258]
0x1400130d4  mov     eax, 0FFFFh
0x1400130d9  mov     r9d, 104h
0x1400130df  mov     [rsp+290h+var_25C], ax
0x1400130e4  mov     [rsp+290h+var_260], ax
0x1400130e9  lea     rax, Format
0x1400130f0  cmovz   r10, rax
0x1400130f4  mov     rdx, r10
0x1400130f7  call    AslPathCombine
0x1400130fc  mov     ebx, eax
0x1400130fe  test    eax, eax
0x140013100  jns     short loc_140013126
0x140013102  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140013109  mov     r8d, 517h
0x14001310f  lea     rdx, aSdbpgetpathapp_1; "SdbpGetPathAppraiser"
0x140013116  mov     dword ptr [rsp+290h+var_270], eax
0x14001311a  mov     ecx, 1
0x14001311f  call    AslLogCallPrintf
0x140013124  jmp     short loc_14001316F
0x140013126  mov     r8, r14
0x140013129  lea     rdx, [rsp+290h+var_260]
0x14001312e  lea     rcx, [rsp+290h+var_25C]
0x140013133  call    SdbpGetProcessHostGuestArchitectures
0x140013138  mov     ebx, eax
0x14001313a  test    eax, eax
0x14001313c  jns     short loc_14001314D
0x14001313e  lea     r9, aSdbpgetprocess; "SdbpGetProcessHostGuestArchitectures fa"...
0x140013145  mov     r8d, 51Dh
0x14001314b  jmp     short loc_14001310F
0x14001314d  movzx   r9d, [rsp+290h+var_25C]
0x140013153  lea     rax, [rsp+290h+var_260]
0x140013158  lea     r8, [rsp+290h+var_240]
0x14001315d  mov     [rsp+290h+var_270], rax
0x140013162  mov     rdx, rdi
0x140013165  mov     rcx, rsi
0x140013168  call    AslEnvGetSysNativeDirPathForGuestBuf
0x14001316d  mov     ebx, eax
0x14001316f  mov     eax, ebx
0x140013171  mov     rcx, [rbp+190h+var_30]
0x140013178  xor     rcx, rsp; StackCookie
0x14001317b  call    __security_check_cookie
0x140013180  add     rsp, 270h
0x140013187  pop     r14
0x140013189  pop     rdi
0x14001318a  pop     rsi
0x14001318b  pop     rbx
0x14001318c  pop     rbp
0x14001318d  retn
```
