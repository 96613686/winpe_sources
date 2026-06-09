# OpenComposedEvent(uint,ulong,void * *)

- ea: `0x180061ea8`
- end: `0x180061f40`
- name: `?OpenComposedEvent@@YAJIKPEAPEAX@Z`
- size: `152`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d710`

## callees

- `0x18001f43c`
- `0x180061ea8`
- `0x180061f48`
- `0x180095130`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180061ef1`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x180061ef1`

## string_xrefs

- `0x180061ed5`: `DwmComposedEvent_`

## pseudocode

```c
__int64 __fastcall OpenComposedEvent(int a1, __int64 a2, void **a3)
{
  HANDLE v4; // rax
  unsigned int v5; // ebx
  WCHAR Name[28]; // [rsp+30h] [rbp-48h] BYREF

  if ( StringCchPrintfW(Name, 0x1Au, L"%s%x", L"DwmComposedEvent_", a1) < 0 )
    return 0;
  v4 = OpenEventW(0x100000u, 0, Name);
  *a3 = v4;
  if ( v4 )
  {
    return 0;
  }
  else
  {
    v5 = -2144980991;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &dword_1800FB9B4, 1u, -2144980991, 0x2Eu, 0);
  }
  return v5;
}

```

## disassembly

```asm
0x180061ea8  push    rbx
0x180061eaa  sub     rsp, 70h
0x180061eae  mov     rax, cs:__security_cookie
0x180061eb5  xor     rax, rsp
0x180061eb8  mov     [rsp+78h+var_10], rax
0x180061ebd  mov     rbx, r8
0x180061ec0  mov     [rsp+78h+var_58], ecx
0x180061ec4  lea     r8, aSX; "%s%x"
0x180061ecb  mov     edx, 1Ah; unsigned __int64
0x180061ed0  lea     rcx, [rsp+78h+Name]; unsigned __int16 *
0x180061ed5  lea     r9, aDwmcomposedeve; "DwmComposedEvent_"
0x180061edc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180061ee1  test    eax, eax
0x180061ee3  js      short loc_180061F29
0x180061ee5  lea     r8, [rsp+78h+Name]; lpName
0x180061eea  xor     edx, edx; bInheritHandle
0x180061eec  mov     ecx, 100000h; dwDesiredAccess
0x180061ef1  call    cs:__imp_OpenEventW
0x180061ef7  mov     [rbx], rax
0x180061efa  test    rax, rax
0x180061efd  jnz     short loc_180061F29
0x180061eff  mov     [rsp+78h+var_50], rax; void *
0x180061f04  lea     r8d, [rax+1]; unsigned int
0x180061f08  mov     ebx, 80263001h
0x180061f0d  mov     [rsp+78h+var_58], 2Eh ; '.'; unsigned int
0x180061f15  mov     r9d, ebx; int
0x180061f18  lea     rdx, dword_1800FB9B4; int *
0x180061f1f  lea     ecx, [rax+14h]; unsigned int
0x180061f22  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180061f27  jmp     short loc_180061F2B
0x180061f29  xor     ebx, ebx
0x180061f2b  mov     eax, ebx
0x180061f2d  mov     rcx, [rsp+78h+var_10]
0x180061f32  xor     rcx, rsp; StackCookie
0x180061f35  call    __security_check_cookie
0x180061f3a  add     rsp, 70h
0x180061f3e  pop     rbx
0x180061f3f  retn
```
