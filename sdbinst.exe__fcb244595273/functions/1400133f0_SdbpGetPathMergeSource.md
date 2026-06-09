# SdbpGetPathMergeSource

- ea: `0x1400133f0`
- end: `0x1400134d3`
- name: `SdbpGetPathMergeSource`
- size: `227`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, installer_update, broker_com_uri`

## callees

- `0x14001008c`
- `0x1400100c4`
- `0x140012db0`
- `0x1400133f0`
- `0x14002e420`

## string_xrefs

- `0x14001347d`: `AslPathCombine failed [%x]`
- `0x14001348e`: `SdbpGetPathMergeSource`

## pseudocode

```c
__int64 __fastcall SdbpGetPathMergeSource(unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 *a3)
{
  unsigned __int16 *v3; // r10
  int v7; // eax
  unsigned int v8; // ebx
  __int128 v9; // [rsp+30h] [rbp-268h] BYREF
  _OWORD v10[2]; // [rsp+40h] [rbp-258h]
  unsigned __int16 v11[264]; // [rsp+60h] [rbp-238h] BYREF

  v3 = a3;
  v9 = *(_OWORD *)L"\\MergeSdbFilesSource";
  v10[0] = *(_OWORD *)L"bFilesSource";
  *(_OWORD *)((char *)v10 + 10) = *(_OWORD *)L"sSource";
  if ( a2 < 0x15 )
    return 3221225507LL;
  *a1 = 0;
  v11[0] = 0;
  if ( !a3 )
    v3 = (unsigned __int16 *)&Format;
  v7 = AslPathCombine(&v9, v3, v11, 260);
  v8 = v7;
  if ( v7 >= 0 )
    return (unsigned int)SdbpGetPathAppPatch(a1, a2, v11);
  else
    AslLogCallPrintf(1, "SdbpGetPathMergeSource", 1136, "AslPathCombine failed [%x]", v7);
  return v8;
}

```

## disassembly

```asm
0x1400133f0  push    rbx
0x1400133f2  push    rsi
0x1400133f3  push    rdi
0x1400133f4  sub     rsp, 280h
0x1400133fb  mov     rax, cs:__security_cookie
0x140013402  xor     rax, rsp
0x140013405  mov     [rsp+298h+var_28], rax
0x14001340d  mov     r10, r8
0x140013410  mov     rsi, rdx
0x140013413  mov     rdi, rcx
0x140013416  movups  xmm0, xmmword ptr cs:aMergesdbfiless; "\\MergeSdbFilesSource"
0x14001341d  movups  xmm1, xmmword ptr cs:aMergesdbfiless+10h; "bFilesSource"
0x140013424  movups  [rsp+298h+var_268], xmm0
0x140013429  movups  xmm0, xmmword ptr cs:aMergesdbfiless+1Ah; "sSource"
0x140013430  movups  xmmword ptr [rsp+298h+var_258], xmm1
0x140013435  movups  xmmword ptr [rsp+298h+var_258+0Ah], xmm0
0x14001343a  cmp     rdx, 15h
0x14001343e  jnb     short loc_140013447
0x140013440  mov     eax, 0C0000023h
0x140013445  jmp     short loc_1400134B8
0x140013447  xor     eax, eax
0x140013449  lea     r8, [rsp+298h+var_238]
0x14001344e  mov     [rcx], ax
0x140013451  test    r10, r10
0x140013454  mov     [rsp+298h+var_238], ax
0x140013459  lea     rcx, [rsp+298h+var_268]
0x14001345e  lea     rax, Format
0x140013465  mov     r9d, 104h
0x14001346b  cmovz   r10, rax
0x14001346f  mov     rdx, r10
0x140013472  call    AslPathCombine
0x140013477  mov     ebx, eax
0x140013479  test    eax, eax
0x14001347b  jns     short loc_1400134A1
0x14001347d  lea     r9, aAslpathcombine_0; "AslPathCombine failed [%x]"
0x140013484  mov     [rsp+298h+var_278], eax
0x140013488  mov     r8d, 470h
0x14001348e  lea     rdx, aSdbpgetpathmer; "SdbpGetPathMergeSource"
0x140013495  mov     ecx, 1
0x14001349a  call    AslLogCallPrintf
0x14001349f  jmp     short loc_1400134B6
0x1400134a1  xor     r9d, r9d
0x1400134a4  lea     r8, [rsp+298h+var_238]
0x1400134a9  mov     rdx, rsi; unsigned __int64
0x1400134ac  mov     rcx, rdi; unsigned __int16 *
0x1400134af  call    SdbpGetPathAppPatch
0x1400134b4  mov     ebx, eax
0x1400134b6  mov     eax, ebx
0x1400134b8  mov     rcx, [rsp+298h+var_28]
0x1400134c0  xor     rcx, rsp; StackCookie
0x1400134c3  call    __security_check_cookie
0x1400134c8  add     rsp, 280h
0x1400134cf  pop     rdi
0x1400134d0  pop     rsi
0x1400134d1  pop     rbx
0x1400134d2  retn
```
