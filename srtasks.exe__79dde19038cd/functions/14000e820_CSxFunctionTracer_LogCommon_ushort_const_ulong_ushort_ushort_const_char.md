# CSxFunctionTracer::_LogCommon(ushort const *,ulong,ushort,ushort const *,char *)

- ea: `0x14000e820`
- end: `0x14000e988`
- name: `?_LogCommon@CSxFunctionTracer@@AEBAXPEBGKG0PEAD@Z`
- size: `360`
- prototype: `void __fastcall(CSxFunctionTracer *this, const unsigned __int16 *, unsigned int, unsigned __int16, wchar_t *Format, va_list Args)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000e7b0`
- `0x14000e7e8`

## callees

- `0x14000e674`
- `0x14000e820`
- `0x14000e990`
- `0x140010980`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x14000e87a`
- `msvcrt!_vsnwprintf` at `0x14000e87a`

## pseudocode

```c
void __fastcall CSxFunctionTracer::_LogCommon(
        CSxFunctionTracer *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 a4,
        wchar_t *Format,
        va_list Args)
{
  int v6; // edi
  _QWORD *v10; // r10
  int v11; // edx
  unsigned __int16 v12; // [rsp+28h] [rbp-860h]
  unsigned __int16 *v13; // [rsp+40h] [rbp-848h] BYREF
  wchar_t Buffer[1024]; // [rsp+50h] [rbp-838h] BYREF

  v6 = a4;
  v13 = 0;
  Buffer[0] = 0;
  if ( Format && (unsigned int)_vsnwprintf(Buffer, 0x3FFu, Format, Args) > 0x3FE )
    Buffer[1023] = 0;
  if ( v6 == 1 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000000) != 0 )
    {
      v11 = 19;
      goto LABEL_15;
    }
  }
  else if ( v6 == 2 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000000) != 0 )
    {
      v11 = 20;
      goto LABEL_15;
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000000) != 0 )
    {
      v11 = 21;
LABEL_15:
      WPP_SF_Ssddd(
        v10[2],
        v11,
        *((unsigned __int16 *)this + 2),
        (unsigned int)Buffer,
        *((_QWORD *)this + 2),
        *((_WORD *)this + 2),
        *((_WORD *)this + 3),
        *(_DWORD *)this,
        v13);
    }
  }
  v13 = Buffer;
  CSxFunctionTracer::LogEvent(
    this,
    a2,
    a3,
    v6,
    *((unsigned __int16 *)this + 3),
    v12,
    (const unsigned __int16 **const)&v13);
}

```

## disassembly

```asm
0x14000e820  push    rbx
0x14000e822  push    rbp
0x14000e823  push    rsi
0x14000e824  push    rdi
0x14000e825  sub     rsp, 868h
0x14000e82c  mov     rax, cs:__security_cookie
0x14000e833  xor     rax, rsp
0x14000e836  mov     [rsp+888h+var_38], rax
0x14000e83e  xor     eax, eax
0x14000e840  movzx   edi, r9w
0x14000e844  mov     r9, [rsp+888h+Args]; Args
0x14000e84c  mov     ebp, r8d
0x14000e84f  mov     r8, [rsp+888h+Format]; Format
0x14000e857  mov     rsi, rdx
0x14000e85a  mov     [rsp+888h+var_848], 0
0x14000e863  mov     rbx, rcx
0x14000e866  mov     [rsp+888h+Buffer], ax
0x14000e86b  test    r8, r8
0x14000e86e  jz      short loc_14000E895
0x14000e870  mov     edx, 3FFh; BufferCount
0x14000e875  lea     rcx, [rsp+888h+Buffer]; Buffer
0x14000e87a  call    cs:__imp__vsnwprintf
0x14000e880  test    eax, eax
0x14000e882  js      short loc_14000E88B
0x14000e884  cmp     eax, 3FFh
0x14000e889  jb      short loc_14000E895
0x14000e88b  xor     eax, eax
0x14000e88d  mov     [rsp+888h+var_3A], ax
0x14000e895  mov     ecx, edi
0x14000e897  sub     ecx, 1
0x14000e89a  jz      short loc_14000E8ED
0x14000e89c  cmp     ecx, 1
0x14000e89f  jz      short loc_14000E8C9
0x14000e8a1  mov     r10, cs:WPP_GLOBAL_Control
0x14000e8a8  lea     rax, WPP_GLOBAL_Control
0x14000e8af  cmp     r10, rax
0x14000e8b2  jz      loc_14000E93E
0x14000e8b8  test    dword ptr [r10+1Ch], 8000000h
0x14000e8c0  jz      short loc_14000E93E
0x14000e8c2  mov     edx, 15h
0x14000e8c7  jmp     short loc_14000E90F
0x14000e8c9  mov     r10, cs:WPP_GLOBAL_Control
0x14000e8d0  lea     rax, WPP_GLOBAL_Control
0x14000e8d7  cmp     r10, rax
0x14000e8da  jz      short loc_14000E93E
0x14000e8dc  test    dword ptr [r10+1Ch], 4000000h
0x14000e8e4  jz      short loc_14000E93E
0x14000e8e6  mov     edx, 14h
0x14000e8eb  jmp     short loc_14000E90F
0x14000e8ed  mov     r10, cs:WPP_GLOBAL_Control
0x14000e8f4  lea     rax, WPP_GLOBAL_Control
0x14000e8fb  cmp     r10, rax
0x14000e8fe  jz      short loc_14000E93E
0x14000e900  test    dword ptr [r10+1Ch], 2000000h
0x14000e908  jz      short loc_14000E93E
0x14000e90a  mov     edx, 13h
0x14000e90f  mov     eax, [rbx]
0x14000e911  lea     r9, [rsp+888h+Buffer]
0x14000e916  movzx   ecx, word ptr [rbx+6]
0x14000e91a  movzx   r8d, word ptr [rbx+4]
0x14000e91f  mov     [rsp+888h+var_850], eax
0x14000e923  mov     rax, [rbx+10h]
0x14000e927  mov     dword ptr [rsp+888h+var_858], ecx
0x14000e92b  mov     rcx, [r10+10h]
0x14000e92f  mov     dword ptr [rsp+888h+var_860], r8d; unsigned __int16
0x14000e934  mov     qword ptr [rsp+888h+var_868], rax
0x14000e939  call    WPP_SF_Ssddd
0x14000e93e  lea     rax, [rsp+888h+Buffer]
0x14000e943  movzx   r9d, di; unsigned __int16
0x14000e947  lea     rcx, [rsp+888h+var_848]
0x14000e94c  mov     [rsp+888h+var_848], rax
0x14000e951  movzx   eax, word ptr [rbx+6]
0x14000e955  mov     r8d, ebp; unsigned int
0x14000e958  mov     [rsp+888h+var_858], rcx; unsigned __int16 **
0x14000e95d  mov     rdx, rsi; unsigned __int16 *
0x14000e960  mov     rcx, rbx; this
0x14000e963  mov     [rsp+888h+var_868], eax; unsigned int
0x14000e967  call    ?LogEvent@CSxFunctionTracer@@QEBAJPEBGKGKGQEAPEBG@Z; CSxFunctionTracer::LogEvent(ushort const *,ulong,ushort,ulong,ushort,ushort const * * const)
0x14000e96c  mov     rcx, [rsp+888h+var_38]
0x14000e974  xor     rcx, rsp; StackCookie
0x14000e977  call    __security_check_cookie
0x14000e97c  add     rsp, 868h
0x14000e983  pop     rdi
0x14000e984  pop     rsi
0x14000e985  pop     rbp
0x14000e986  pop     rbx
0x14000e987  retn
```
