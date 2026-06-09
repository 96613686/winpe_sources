# LOG_WRITER::NeedToRolloverToNewLogFile(unsigned __int64,ulong)

- ea: `0x180005960`
- end: `0x180005b34`
- name: `?NeedToRolloverToNewLogFile@LOG_WRITER@@AEAAH_KK@Z`
- size: `468`
- prototype: `__int64 __fastcall(LOG_WRITER *this, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004fe4`
- `0x180005458`

## callees

- `0x180005960`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800059d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800059d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800059c6`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800059c6`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::NeedToRolloverToNewLogFile(LOG_WRITER *this, __int64 a2, unsigned int a3)
{
  _DWORD *v3; // rax
  unsigned int v5; // esi
  bool v6; // zf
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  unsigned int v9; // r8d
  int v10; // ecx
  unsigned int v11; // ecx
  struct _SYSTEMTIME SystemTime; // [rsp+20h] [rbp-28h] BYREF

  v3 = (_DWORD *)*((_QWORD *)this + 1);
  if ( v3[6] )
  {
    v5 = 0;
    SystemTime = 0;
    if ( v3 && v3[1] == 1 )
      GetLocalTime(&SystemTime);
    else
      GetSystemTime(&SystemTime);
    switch ( *(_DWORD *)(*((_QWORD *)this + 1) + 24LL) )
    {
      case 1:
        if ( *((_WORD *)this + 324) != SystemTime.wYear || *((_WORD *)this + 325) != SystemTime.wMonth )
          return 1;
        v6 = *((_WORD *)this + 327) == SystemTime.wDay;
        break;
      case 2:
        v7 = SystemTime.wDay - SystemTime.wDayOfWeek;
        if ( v7 )
        {
          v8 = v7 / 7 + 1;
          if ( v7 != 7 * (v7 / 7) )
            v8 = v7 / 7 + 2;
        }
        else
        {
          v8 = 1;
        }
        v9 = *((unsigned __int16 *)this + 327) - *((unsigned __int16 *)this + 326);
        if ( v9 )
        {
          v11 = v9 / 7;
          if ( v9 == 7 * (v9 / 7) )
            v10 = v11 + 1;
          else
            v10 = v11 + 2;
        }
        else
        {
          v10 = 1;
        }
        if ( *((_WORD *)this + 324) != SystemTime.wYear || *((_WORD *)this + 325) != SystemTime.wMonth )
          return 1;
        v6 = v10 == v8;
        break;
      case 3:
        if ( *((_WORD *)this + 324) != SystemTime.wYear )
          return 1;
        v6 = *((_WORD *)this + 325) == SystemTime.wMonth;
        break;
      case 4:
        if ( *((_WORD *)this + 324) != SystemTime.wYear
          || *((_WORD *)this + 325) != SystemTime.wMonth
          || *((_WORD *)this + 327) != SystemTime.wDay )
        {
          return 1;
        }
        v6 = *((_WORD *)this + 328) == SystemTime.wHour;
        break;
      default:
        return v5;
    }
    if ( v6 )
      return v5;
    return 1;
  }
  return v3[7] != -1 && a2 + (unsigned __int64)a3 > (unsigned int)v3[7];
}

```

## disassembly

```asm
0x180005960  push    rbp
0x180005962  push    rbx
0x180005963  push    rsi
0x180005964  push    rdi
0x180005965  mov     rbp, rsp
0x180005968  sub     rsp, 48h
0x18000596c  mov     rax, cs:__security_cookie
0x180005973  xor     rax, rsp
0x180005976  mov     [rbp+var_18], rax
0x18000597a  mov     rax, [rcx+8]
0x18000597e  mov     rbx, rcx
0x180005981  cmp     dword ptr [rax+18h], 0
0x180005985  jnz     short loc_1800059AC
0x180005987  cmp     dword ptr [rax+1Ch], 0FFFFFFFFh
0x18000598b  jz      short loc_1800059A5
0x18000598d  mov     eax, [rax+1Ch]
0x180005990  mov     ecx, r8d
0x180005993  add     rcx, rdx
0x180005996  cmp     rcx, rax
0x180005999  jbe     short loc_1800059A5
0x18000599b  mov     esi, 1
0x1800059a0  jmp     loc_180005B1D
0x1800059a5  xor     esi, esi
0x1800059a7  jmp     loc_180005B1D
0x1800059ac  xor     esi, esi
0x1800059ae  xorps   xmm0, xmm0
0x1800059b1  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x1800059b5  lea     edi, [rsi+1]
0x1800059b8  test    rax, rax
0x1800059bb  jz      short loc_1800059CE
0x1800059bd  cmp     [rax+4], edi
0x1800059c0  jnz     short loc_1800059CE
0x1800059c2  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800059c6  call    cs:__imp_GetLocalTime
0x1800059cc  jmp     short loc_1800059D8
0x1800059ce  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x1800059d2  call    cs:__imp_GetSystemTime
0x1800059d8  mov     rcx, [rbx+8]
0x1800059dc  mov     edx, [rcx+18h]
0x1800059df  sub     edx, edi
0x1800059e1  jz      loc_180005AF4
0x1800059e7  sub     edx, edi
0x1800059e9  jz      short loc_180005A5B
0x1800059eb  sub     edx, edi
0x1800059ed  jz      short loc_180005A3A
0x1800059ef  cmp     edx, edi
0x1800059f1  jnz     loc_180005B1D
0x1800059f7  movzx   eax, [rbp+SystemTime.wYear]
0x1800059fb  cmp     [rbx+288h], ax
0x180005a02  jnz     loc_180005B1B
0x180005a08  movzx   eax, [rbp+SystemTime.wMonth]
0x180005a0c  cmp     [rbx+28Ah], ax
0x180005a13  jnz     loc_180005B1B
0x180005a19  movzx   eax, [rbp+SystemTime.wDay]
0x180005a1d  cmp     [rbx+28Eh], ax
0x180005a24  jnz     loc_180005B1B
0x180005a2a  movzx   eax, [rbp+SystemTime.wHour]
0x180005a2e  cmp     [rbx+290h], ax
0x180005a35  jmp     loc_180005B19
0x180005a3a  movzx   eax, [rbp+SystemTime.wYear]
0x180005a3e  cmp     [rbx+288h], ax
0x180005a45  jnz     loc_180005B1B
0x180005a4b  movzx   eax, [rbp+SystemTime.wMonth]
0x180005a4f  cmp     [rbx+28Ah], ax
0x180005a56  jmp     loc_180005B19
0x180005a5b  movzx   eax, [rbp+SystemTime.wDayOfWeek]
0x180005a5f  mov     r10d, 24924925h
0x180005a65  movzx   r8d, [rbp+SystemTime.wDay]
0x180005a6a  sub     r8d, eax
0x180005a6d  cmp     r8d, edi
0x180005a70  jnb     short loc_180005A77
0x180005a72  mov     r9d, edi
0x180005a75  jmp     short loc_180005A99
0x180005a77  mov     eax, r10d
0x180005a7a  mov     ecx, r8d
0x180005a7d  mul     r8d
0x180005a80  sub     ecx, edx
0x180005a82  shr     ecx, 1
0x180005a84  add     ecx, edx
0x180005a86  shr     ecx, 2
0x180005a89  imul    eax, ecx, 7
0x180005a8c  lea     r9d, [rcx+1]
0x180005a90  cmp     r8d, eax
0x180005a93  jz      short loc_180005A99
0x180005a95  lea     r9d, [rcx+2]
0x180005a99  movzx   r8d, word ptr [rbx+28Eh]
0x180005aa1  movzx   eax, word ptr [rbx+28Ch]
0x180005aa8  sub     r8d, eax
0x180005aab  cmp     r8d, edi
0x180005aae  jnb     short loc_180005AB4
0x180005ab0  mov     ecx, edi
0x180005ab2  jmp     short loc_180005AD5
0x180005ab4  mov     eax, r10d
0x180005ab7  mov     ecx, r8d
0x180005aba  mul     r8d
0x180005abd  sub     ecx, edx
0x180005abf  shr     ecx, 1
0x180005ac1  add     ecx, edx
0x180005ac3  shr     ecx, 2
0x180005ac6  imul    eax, ecx, 7
0x180005ac9  cmp     r8d, eax
0x180005acc  jnz     short loc_180005AD2
0x180005ace  inc     ecx
0x180005ad0  jmp     short loc_180005AD5
0x180005ad2  add     ecx, 2
0x180005ad5  movzx   eax, [rbp+SystemTime.wYear]
0x180005ad9  cmp     [rbx+288h], ax
0x180005ae0  jnz     short loc_180005B1B
0x180005ae2  movzx   eax, [rbp+SystemTime.wMonth]
0x180005ae6  cmp     [rbx+28Ah], ax
0x180005aed  jnz     short loc_180005B1B
0x180005aef  cmp     ecx, r9d
0x180005af2  jmp     short loc_180005B19
0x180005af4  movzx   eax, [rbp+SystemTime.wYear]
0x180005af8  cmp     [rbx+288h], ax
0x180005aff  jnz     short loc_180005B1B
0x180005b01  movzx   eax, [rbp+SystemTime.wMonth]
0x180005b05  cmp     [rbx+28Ah], ax
0x180005b0c  jnz     short loc_180005B1B
0x180005b0e  movzx   eax, [rbp+SystemTime.wDay]
0x180005b12  cmp     [rbx+28Eh], ax
0x180005b19  jz      short loc_180005B1D
0x180005b1b  mov     esi, edi
0x180005b1d  mov     eax, esi
0x180005b1f  mov     rcx, [rbp+var_18]
0x180005b23  xor     rcx, rsp; StackCookie
0x180005b26  call    __security_check_cookie
0x180005b2b  add     rsp, 48h
0x180005b2f  pop     rdi
0x180005b30  pop     rsi
0x180005b31  pop     rbx
0x180005b32  pop     rbp
0x180005b33  retn
```
