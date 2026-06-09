# MilInstrumentationBreak(ulong,bool)

- ea: `0x18002b5cc`
- end: `0x18002b673`
- name: `?MilInstrumentationBreak@@YAXK_N@Z`
- size: `167`
- prototype: `void(unsigned int, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002b434`

## callees

- `0x18002b594`
- `0x18002b5cc`
- `0x18002b6f8`
- `0x18002b76c`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b614`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b614`
- `ntdll!NtQuerySystemInformation` at `0x18002b637`
- `ntdll!NtQuerySystemInformation` at `0x18002b637`

## string_xrefs

- `0x18002b656`: `onecoreuap\windows\dwm\common\util\utillib\debugbreak.cpp`

## pseudocode

```c
void __fastcall MilInstrumentationBreak(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  char v2; // bl
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v5; // [rsp+38h] [rbp+10h] BYREF

  LOBYTE(v5) = (_BYTE)a2;
  v2 = (char)a1;
  if ( !g_fDisableInstrumentationBreaks )
  {
    v5 = 0;
    if ( RegGetHKLMDword(a1, a2, &v5) && !v5 )
    {
      if ( (v2 & 8) == 0 || (unsigned int)IsKernelDebuggerPresent() )
        goto LABEL_10;
      if ( !IsDebuggerPresent() )
      {
        if ( !byte_180042C1A )
          byte_180042C1A = NtQuerySystemInformation(SystemKernelDebuggerInformation, &byte_180042C18, 2u, 0) >= 0;
        if ( byte_180042C18 )
LABEL_10:
          wil::details::in1diag3::Log_Hr(
            retaddr,
            (void *)0xD6,
            (unsigned int)"onecoreuap\\windows\\dwm\\common\\util\\utillib\\debugbreak.cpp",
            (const char *)0x8007029CLL,
            v3);
      }
    }
  }
}

```

## disassembly

```asm
0x18002b5cc  mov     byte ptr [rsp+arg_8], dl
0x18002b5d0  push    rbx; int
0x18002b5d1  sub     rsp, 20h
0x18002b5d5  cmp     cs:?g_fDisableInstrumentationBreaks@@3_NA, 0; bool g_fDisableInstrumentationBreaks
0x18002b5dc  mov     ebx, ecx
0x18002b5de  jnz     loc_18002B66D
0x18002b5e4  lea     r8, [rsp+28h+arg_8]; unsigned int *
0x18002b5e9  mov     [rsp+28h+arg_8], 0
0x18002b5f1  call    ?RegGetHKLMDword@@YA_NQEBG0PEAK@Z; RegGetHKLMDword(ushort const * const,ushort const * const,ulong *)
0x18002b5f6  test    al, al
0x18002b5f8  jz      short loc_18002B66D
0x18002b5fa  cmp     [rsp+28h+arg_8], 0
0x18002b5ff  setz    al
0x18002b602  test    al, al
0x18002b604  jz      short loc_18002B66D
0x18002b606  test    bl, 8
0x18002b609  jz      short loc_18002B651
0x18002b60b  call    ?IsKernelDebuggerPresent@@YAHXZ; IsKernelDebuggerPresent(void)
0x18002b610  test    eax, eax
0x18002b612  jnz     short loc_18002B651
0x18002b614  call    cs:__imp_IsDebuggerPresent
0x18002b61a  test    eax, eax
0x18002b61c  jnz     short loc_18002B66D
0x18002b61e  cmp     cs:byte_180042C1A, al
0x18002b624  jnz     short loc_18002B648
0x18002b626  xor     r9d, r9d; ReturnLength
0x18002b629  lea     r8d, [rax+2]; SystemInformationLength
0x18002b62d  lea     rdx, byte_180042C18; SystemInformation
0x18002b634  lea     ecx, [rax+23h]; SystemInformationClass
0x18002b637  call    cs:__imp_NtQuerySystemInformation
0x18002b63d  test    eax, eax
0x18002b63f  js      short loc_18002B648
0x18002b641  mov     cs:byte_180042C1A, 1
0x18002b648  cmp     cs:byte_180042C18, 0
0x18002b64f  jz      short loc_18002B66D
0x18002b651  mov     rcx, [rsp+28h]; this
0x18002b656  lea     r8, aOnecoreuapWind_6; "onecoreuap\\windows\\dwm\\common\\util"...
0x18002b65d  mov     r9d, 8007029Ch; char *
0x18002b663  mov     edx, 0D6h; void *
0x18002b668  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002b66d  add     rsp, 20h
0x18002b671  pop     rbx
0x18002b672  retn
```
