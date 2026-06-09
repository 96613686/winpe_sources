# CSxFunctionTracer::_LogCommon(ushort const *,ulong,ushort,ushort const *,char *)

- ea: `0x18000d800`
- end: `0x18000d906`
- name: `?_LogCommon@CSxFunctionTracer@@AEBAXPEBGKG0PEAD@Z`
- size: `262`
- prototype: `void __fastcall(CSxFunctionTracer *this, const unsigned __int16 *, unsigned int, __int64, wchar_t *Format, va_list Args)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d7d0`

## callees

- `0x18000d69c`
- `0x18000d800`
- `0x18000d90c`
- `0x1800157f0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000d855`
- `msvcrt!_vsnwprintf` at `0x18000d855`

## pseudocode

```c
void __fastcall CSxFunctionTracer::_LogCommon(
        CSxFunctionTracer *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        __int64 a4,
        wchar_t *Format,
        va_list Args)
{
  unsigned __int16 v6; // r9
  int v8; // r8d
  unsigned __int16 v11; // [rsp+28h] [rbp-850h]
  int v12; // [rsp+38h] [rbp-840h]
  unsigned __int16 *v13; // [rsp+40h] [rbp-838h] BYREF
  wchar_t Buffer[1024]; // [rsp+50h] [rbp-828h] BYREF

  v6 = (unsigned __int16)Args;
  v13 = 0;
  v8 = (int)Format;
  Buffer[0] = 0;
  if ( Format && (unsigned int)_vsnwprintf(Buffer, 0x3FFu, Format, Args) > 0x3FE )
    Buffer[1023] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
  {
    v12 = *(_DWORD *)this;
    WPP_SF_Ssddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      v8,
      (unsigned int)Buffer,
      *((_QWORD *)this + 2),
      *((_WORD *)this + 2),
      *((_WORD *)this + 3),
      v12,
      v13);
  }
  v13 = Buffer;
  CSxFunctionTracer::LogEvent(
    this,
    a2,
    a3,
    v6,
    *((unsigned __int16 *)this + 3),
    v11,
    (const unsigned __int16 **const)&v13);
}

```

## disassembly

```asm
0x18000d800  push    rbx
0x18000d802  push    rsi
0x18000d803  push    rdi
0x18000d804  sub     rsp, 860h
0x18000d80b  mov     rax, cs:__security_cookie
0x18000d812  xor     rax, rsp
0x18000d815  mov     [rsp+878h+var_28], rax
0x18000d81d  mov     r9, [rsp+878h+Args]; Args
0x18000d825  xor     eax, eax
0x18000d827  mov     esi, r8d
0x18000d82a  mov     [rsp+878h+var_838], 0
0x18000d833  mov     r8, [rsp+878h+Format]; Format
0x18000d83b  mov     rdi, rdx
0x18000d83e  mov     [rsp+878h+Buffer], ax
0x18000d843  mov     rbx, rcx
0x18000d846  test    r8, r8
0x18000d849  jz      short loc_18000D870
0x18000d84b  mov     edx, 3FFh; BufferCount
0x18000d850  lea     rcx, [rsp+878h+Buffer]; Buffer
0x18000d855  call    cs:__imp__vsnwprintf
0x18000d85b  test    eax, eax
0x18000d85d  js      short loc_18000D866
0x18000d85f  cmp     eax, 3FFh
0x18000d864  jb      short loc_18000D870
0x18000d866  xor     eax, eax
0x18000d868  mov     [rsp+878h+var_2A], ax
0x18000d870  mov     r10, cs:WPP_GLOBAL_Control
0x18000d877  lea     rax, WPP_GLOBAL_Control
0x18000d87e  cmp     r10, rax
0x18000d881  jz      short loc_18000D8C1
0x18000d883  test    dword ptr [r10+1Ch], 2000000h
0x18000d88b  jz      short loc_18000D8C1
0x18000d88d  movzx   ecx, word ptr [rbx+6]
0x18000d891  mov     edx, 13h
0x18000d896  mov     eax, [rbx]
0x18000d898  movzx   r9d, word ptr [rbx+4]
0x18000d89d  mov     [rsp+878h+var_840], eax
0x18000d8a1  mov     rax, [rbx+10h]
0x18000d8a5  mov     dword ptr [rsp+878h+var_848], ecx
0x18000d8a9  mov     rcx, [r10+10h]
0x18000d8ad  mov     dword ptr [rsp+878h+var_850], r9d; unsigned __int16
0x18000d8b2  lea     r9, [rsp+878h+Buffer]
0x18000d8b7  mov     qword ptr [rsp+878h+var_858], rax
0x18000d8bc  call    WPP_SF_Ssddd
0x18000d8c1  lea     rax, [rsp+878h+Buffer]
0x18000d8c6  mov     r8d, esi; unsigned int
0x18000d8c9  lea     rcx, [rsp+878h+var_838]
0x18000d8ce  mov     [rsp+878h+var_838], rax
0x18000d8d3  movzx   eax, word ptr [rbx+6]
0x18000d8d7  mov     rdx, rdi; unsigned __int16 *
0x18000d8da  mov     [rsp+878h+var_848], rcx; unsigned __int16 **
0x18000d8df  mov     rcx, rbx; this
0x18000d8e2  mov     [rsp+878h+var_858], eax; unsigned int
0x18000d8e6  call    ?LogEvent@CSxFunctionTracer@@QEBAJPEBGKGKGQEAPEBG@Z; CSxFunctionTracer::LogEvent(ushort const *,ulong,ushort,ulong,ushort,ushort const * * const)
0x18000d8eb  mov     rcx, [rsp+878h+var_28]
0x18000d8f3  xor     rcx, rsp; StackCookie
0x18000d8f6  call    __security_check_cookie
0x18000d8fb  add     rsp, 860h
0x18000d902  pop     rdi
0x18000d903  pop     rsi
0x18000d904  pop     rbx
0x18000d905  retn
```
