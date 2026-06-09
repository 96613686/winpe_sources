# AslPathToSystemPathBuf

- ea: `0x1400103d8`
- end: `0x140010478`
- name: `AslPathToSystemPathBuf`
- size: `160`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x14000f158`
- `0x14000f28c`
- `0x14001031c`
- `0x140012db0`

## callees

- `0x14000acf4`
- `0x14001008c`
- `0x1400102a0`
- `0x1400103d8`
- `0x140011d6c`
- `0x14002e3e2`

## string_xrefs

- `0x14001040e`: `Failed to get system root directory [%x]`
- `0x14001041f`: `AslPathToSystemPathBuf`
- `0x140010457`: `AslPathToSystemPathBuf`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPathBuf(unsigned __int16 *a1, __int64 a2, unsigned __int16 *a3)
{
  __int64 NtSystemRoot; // rax
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax

  memset_0(a1, 0, 2 * a2);
  NtSystemRoot = AslPathGetNtSystemRoot();
  v7 = RtlStringCchCopyW(a1, a2, NtSystemRoot);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v9 = RtlStringCchCatW(a1, a2, a3);
    v8 = v9;
    if ( v9 < 0 )
    {
      AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1488, "Failed to cat string [%x]", v9);
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1477, "Failed to get system root directory [%x]", v7);
  }
  return v8;
}

```

## disassembly

```asm
0x1400103d8  push    rbx
0x1400103da  push    rbp
0x1400103db  push    rsi
0x1400103dc  push    rdi
0x1400103dd  sub     rsp, 38h
0x1400103e1  mov     rbp, r8
0x1400103e4  mov     rdi, rdx
0x1400103e7  lea     r8, [rdx+rdx]; Size
0x1400103eb  mov     rsi, rcx
0x1400103ee  xor     edx, edx; Val
0x1400103f0  call    memset_0
0x1400103f5  call    AslPathGetNtSystemRoot
0x1400103fa  mov     r8, rax
0x1400103fd  mov     rdx, rdi
0x140010400  mov     rcx, rsi
0x140010403  call    RtlStringCchCopyW
0x140010408  mov     ebx, eax
0x14001040a  test    eax, eax
0x14001040c  jns     short loc_140010432
0x14001040e  lea     r9, aFailedToGetSys; "Failed to get system root directory [%x"...
0x140010415  mov     [rsp+58h+var_38], eax
0x140010419  mov     r8d, 5C5h
0x14001041f  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x140010426  mov     ecx, 1
0x14001042b  call    AslLogCallPrintf
0x140010430  jmp     short loc_14001046D
0x140010432  mov     r8, rbp; unsigned __int16 *
0x140010435  mov     rdx, rdi; unsigned __int64
0x140010438  mov     rcx, rsi; unsigned __int16 *
0x14001043b  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140010440  mov     ebx, eax
0x140010442  test    eax, eax
0x140010444  jns     short loc_14001046D
0x140010446  lea     r9, aFailedToCatStr; "Failed to cat string [%x]"
0x14001044d  mov     [rsp+58h+var_38], eax
0x140010451  mov     r8d, 5D0h
0x140010457  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x14001045e  mov     ecx, 1
0x140010463  call    AslLogCallPrintf
0x140010468  mov     ebx, 0C000000Dh
0x14001046d  mov     eax, ebx
0x14001046f  add     rsp, 38h
0x140010473  pop     rdi
0x140010474  pop     rsi
0x140010475  pop     rbp
0x140010476  pop     rbx
0x140010477  retn
```
