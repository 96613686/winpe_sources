# SIPolicyIsSystemPolicy

- ea: `0x180020624`
- end: `0x1800207c9`
- name: `SIPolicyIsSystemPolicy`
- size: `421`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180047a80`
- `0x1800492f8`

## callees

- `0x1800205e0`
- `0x180020624`

## pseudocode

```c
char __fastcall SIPolicyIsSystemPolicy(_QWORD *a1)
{
  char v1; // r11
  __int64 v3; // rcx
  __int64 *v4; // rdx
  _QWORD *v5; // r10

  v1 = 1;
  v3 = 1;
  while ( 1 )
  {
    v4 = &g_SiPolicyLegacyIDs[2 * v3];
    if ( *a1 == *v4 && a1[1] == v4[1] )
      break;
    if ( (unsigned __int64)++v3 >= 6 )
    {
      if ( !SIPolicyGetSystemPolicyDefinitionByID(a1)
        && (*v5 != SiPolicyIDNightsWatch || v5[1] != 0xD6CA3031938AA1ADuLL)
        && (*v5 != SiPolicyIDNightsWatchFlight || v5[1] != 0x2D5091C9D8EB5BBCLL)
        && (*v5 != SiPolicyIDNightsWatchTest || v5[1] != 0x5A71493C1DD38EB5LL)
        && *(_OWORD *)v5 != SiPolicyIDNightsWatchDesktop
        && (*v5 != SiPolicyIDNightsWatchDesktopFlight || v5[1] != 0x2D5091C9D8EB5BBCLL)
        && (*v5 != SiPolicyIDNightsWatchDesktopTest || v5[1] != 0x5A71493C1DD38EB5LL)
        && *(_OWORD *)v5 != SiPolicyIDNightsWatchDesktopEval
        && (*v5 != SiPolicyIDNightsWatchDesktopEvalFlight || v5[1] != 0x2D5091C9D8EB5BBCLL)
        && (*v5 != SiPolicyIDNightsWatchDesktopEvalTest || v5[1] != 0x5A71493C1DD38EB5LL)
        && (*v5 != SiPolicyIDEModeBase || v5[1] != 0xF3B900DC0DF4A896uLL)
        && (*v5 != SiPolicyIDEModeFlight || v5[1] != 0x702E1617996449ABLL)
        && (*v5 != SiPolicyIDEModeTest || v5[1] != 0x523A47B6F23D38AALL) )
      {
        return 0;
      }
      return v1;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180020624  sub     rsp, 28h
0x180020628  mov     r11d, 1
0x18002062e  mov     r10, rcx
0x180020631  mov     ecx, r11d
0x180020634  lea     rax, g_SiPolicyLegacyIDs
0x18002063b  mov     rdx, rcx
0x18002063e  shl     rdx, 4
0x180020642  add     rdx, rax
0x180020645  mov     rax, [r10]
0x180020648  cmp     rax, [rdx]
0x18002064b  jnz     short loc_18002065B
0x18002064d  mov     rax, [r10+8]
0x180020651  cmp     rax, [rdx+8]
0x180020655  jz      loc_1800207C0
0x18002065b  add     rcx, r11
0x18002065e  cmp     rcx, 6
0x180020662  jb      short loc_180020634
0x180020664  mov     rcx, r10
0x180020667  call    SIPolicyGetSystemPolicyDefinitionByID
0x18002066c  test    rax, rax
0x18002066f  jnz     loc_1800207C0
0x180020675  mov     rax, [r10]
0x180020678  cmp     rax, cs:SiPolicyIDNightsWatch
0x18002067f  jnz     short loc_180020692
0x180020681  mov     rax, [r10+8]
0x180020685  cmp     rax, cs:qword_180037588
0x18002068c  jz      loc_1800207C0
0x180020692  mov     rax, [r10]
0x180020695  cmp     rax, cs:SiPolicyIDNightsWatchFlight
0x18002069c  jnz     short loc_1800206AF
0x18002069e  mov     rax, [r10+8]
0x1800206a2  cmp     rax, cs:qword_180037428
0x1800206a9  jz      loc_1800207C0
0x1800206af  mov     rax, [r10]
0x1800206b2  cmp     rax, cs:SiPolicyIDNightsWatchTest
0x1800206b9  jnz     short loc_1800206CC
0x1800206bb  mov     rax, [r10+8]
0x1800206bf  cmp     rax, cs:qword_180037500
0x1800206c6  jz      loc_1800207C0
0x1800206cc  mov     rax, [r10]
0x1800206cf  cmp     rax, qword ptr cs:SiPolicyIDNightsWatchDesktop
0x1800206d6  jnz     short loc_1800206E9
0x1800206d8  mov     rax, [r10+8]
0x1800206dc  cmp     rax, qword ptr cs:SiPolicyIDNightsWatchDesktop+8
0x1800206e3  jz      loc_1800207C0
0x1800206e9  mov     rax, [r10]
0x1800206ec  cmp     rax, cs:SiPolicyIDNightsWatchDesktopFlight
0x1800206f3  jnz     short loc_180020706
0x1800206f5  mov     rax, [r10+8]
0x1800206f9  cmp     rax, cs:qword_180037600
0x180020700  jz      loc_1800207C0
0x180020706  mov     rax, [r10]
0x180020709  cmp     rax, cs:SiPolicyIDNightsWatchDesktopTest
0x180020710  jnz     short loc_180020723
0x180020712  mov     rax, [r10+8]
0x180020716  cmp     rax, cs:qword_180037620
0x18002071d  jz      loc_1800207C0
0x180020723  mov     rax, [r10]
0x180020726  cmp     rax, qword ptr cs:SiPolicyIDNightsWatchDesktopEval
0x18002072d  jnz     short loc_180020740
0x18002072f  mov     rax, [r10+8]
0x180020733  cmp     rax, qword ptr cs:SiPolicyIDNightsWatchDesktopEval+8
0x18002073a  jz      loc_1800207C0
0x180020740  mov     rax, [r10]
0x180020743  cmp     rax, cs:SiPolicyIDNightsWatchDesktopEvalFlight
0x18002074a  jnz     short loc_180020759
0x18002074c  mov     rax, [r10+8]
0x180020750  cmp     rax, cs:qword_180037498
0x180020757  jz      short loc_1800207C0
0x180020759  mov     rax, [r10]
0x18002075c  cmp     rax, cs:SiPolicyIDNightsWatchDesktopEvalTest
0x180020763  jnz     short loc_180020772
0x180020765  mov     rax, [r10+8]
0x180020769  cmp     rax, cs:qword_180037438
0x180020770  jz      short loc_1800207C0
0x180020772  mov     rax, [r10]
0x180020775  cmp     rax, cs:SiPolicyIDEModeBase
0x18002077c  jnz     short loc_18002078B
0x18002077e  mov     rax, [r10+8]
0x180020782  cmp     rax, cs:qword_1800374A8
0x180020789  jz      short loc_1800207C0
0x18002078b  mov     rax, [r10]
0x18002078e  cmp     rax, cs:SiPolicyIDEModeFlight
0x180020795  jnz     short loc_1800207A4
0x180020797  mov     rax, [r10+8]
0x18002079b  cmp     rax, cs:qword_180037448
0x1800207a2  jz      short loc_1800207C0
0x1800207a4  mov     rax, [r10]
0x1800207a7  cmp     rax, cs:SiPolicyIDEModeTest
0x1800207ae  jnz     short loc_1800207BD
0x1800207b0  mov     rax, [r10+8]
0x1800207b4  cmp     rax, cs:qword_1800375D8
0x1800207bb  jz      short loc_1800207C0
0x1800207bd  xor     r11b, r11b
0x1800207c0  mov     al, r11b
0x1800207c3  add     rsp, 28h
0x1800207c7  retn
```
