# CConsistentFileMapping::UpdateFileMappingHandle(unsigned __int64)

- ea: `0x180018760`
- end: `0x1800188c6`
- name: `?UpdateFileMappingHandle@CConsistentFileMapping@@MEAAH_K@Z`
- size: `358`
- prototype: `__int64 __fastcall(CConsistentFileMapping *__hidden this, unsigned __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, installer_update`

## callees

- `0x180005e18`
- `0x180010400`
- `0x18001541c`
- `0x180018760`
- `0x180027510`
- `0x18002a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CConsistentFileMapping::UpdateFileMappingHandle(CConsistentFileMapping *this, unsigned __int64 a2)
{
  int v2; // edi
  unsigned __int64 v4; // rsi
  __int64 v6; // rax
  _QWORD v7[2]; // [rsp+40h] [rbp-40h] BYREF
  unsigned __int16 v8[8]; // [rsp+50h] [rbp-30h] BYREF
  __int128 v9; // [rsp+60h] [rbp-20h]
  __int64 v10; // [rsp+70h] [rbp-10h]

  v7[1] = -2;
  v2 = a2;
  v4 = HIDWORD(a2);
  if ( a2 )
    **((_QWORD **)this + 1) = a2;
  if ( *((_QWORD *)this + 5) == **((_QWORD **)this + 1) && *((_QWORD *)this + 3) )
    return 1;
  *(_OWORD *)v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( (int)StringCchPrintfW(v8, 0x14u, L"FM.%I64x", **((_QWORD **)this + 1)) < 0 )
    HIWORD(v10) = 0;
  v7[0] = 0;
  if ( CObjectName::Init((CObjectName *)v7, *((const unsigned __int16 **)this + 10), v8) )
  {
    if ( *((_QWORD *)this + 3) )
      (*(void (__fastcall **)(struct IKernel32Interface *))(*(_QWORD *)g_Kernel32 + 200LL))(g_Kernel32);
    v6 = (*(__int64 (__fastcall **)(struct IKernel32Interface *, _QWORD, _QWORD, _QWORD, _DWORD, int, _QWORD))(*(_QWORD *)g_Kernel32 + 592LL))(
           g_Kernel32,
           *((_QWORD *)this + 2),
           0,
           (unsigned int)(*((_DWORD *)this + 14) | *((_DWORD *)this + 16)),
           v4,
           v2,
           v7[0]);
    *((_QWORD *)this + 3) = v6;
    if ( v6 )
    {
      *((_QWORD *)this + 5) = **((_QWORD **)this + 1);
      CObjectName::Close((CObjectName *)v7);
      return 1;
    }
  }
  CObjectName::Close((CObjectName *)v7);
  return 0;
}

```

## disassembly

```asm
0x180018760  mov     rax, rsp
0x180018763  push    rbp
0x180018764  push    rsi
0x180018765  push    rdi
0x180018766  mov     rbp, rsp
0x180018769  sub     rsp, 80h
0x180018770  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x180018778  mov     [rax+18h], rbx
0x18001877c  mov     rax, cs:__security_cookie
0x180018783  xor     rax, rsp
0x180018786  mov     [rbp+var_8], rax
0x18001878a  mov     rdi, rdx
0x18001878d  mov     rbx, rcx
0x180018790  mov     rsi, rdx
0x180018793  shr     rsi, 20h
0x180018797  test    rdx, rdx
0x18001879a  jz      short loc_1800187A3
0x18001879c  mov     rax, [rcx+8]
0x1800187a0  mov     [rax], rdx
0x1800187a3  mov     rax, [rcx+8]
0x1800187a7  mov     rax, [rax]
0x1800187aa  cmp     [rcx+28h], rax
0x1800187ae  jnz     short loc_1800187C1
0x1800187b0  cmp     qword ptr [rcx+18h], 0
0x1800187b5  jz      short loc_1800187C1
0x1800187b7  mov     eax, 1
0x1800187bc  jmp     loc_1800188A6
0x1800187c1  xorps   xmm0, xmm0
0x1800187c4  xor     eax, eax
0x1800187c6  movups  xmmword ptr [rbp+var_30], xmm0
0x1800187ca  movups  [rbp+var_20], xmm0
0x1800187ce  mov     [rbp+var_10], rax
0x1800187d2  mov     r9, [rcx+8]
0x1800187d6  mov     r9, [r9]
0x1800187d9  lea     r8, aFmI64x; "FM.%I64x"
0x1800187e0  lea     edx, [rax+14h]; unsigned __int64
0x1800187e3  lea     rcx, [rbp+var_30]; unsigned __int16 *
0x1800187e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800187ec  test    eax, eax
0x1800187ee  jns     short loc_1800187F6
0x1800187f0  xor     eax, eax
0x1800187f2  mov     word ptr [rbp+var_10+6], ax
0x1800187f6  mov     [rbp+var_40], 0
0x1800187fe  lea     r8, [rbp+var_30]; unsigned __int16 *
0x180018802  mov     rdx, [rbx+50h]; unsigned __int16 *
0x180018806  lea     rcx, [rbp+var_40]; this
0x18001880a  call    ?Init@CObjectName@@QEAAHPEBG0@Z; CObjectName::Init(ushort const *,ushort const *)
0x18001880f  test    eax, eax
0x180018811  jnz     short loc_180018822
0x180018813  lea     rcx, [rbp+var_40]; this
0x180018817  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x18001881c  nop
0x18001881d  jmp     loc_1800188A4
0x180018822  mov     rdx, [rbx+18h]
0x180018826  test    rdx, rdx
0x180018829  jz      short loc_180018841
0x18001882b  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180018832  mov     rax, [rcx]
0x180018835  mov     rax, [rax+0C8h]
0x18001883c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018841  mov     rcx, cs:?g_Kernel32@@3PEAUIKernel32Interface@@EA; IKernel32Interface * g_Kernel32
0x180018848  mov     rax, [rcx]
0x18001884b  mov     r9d, [rbx+40h]
0x18001884f  or      r9d, [rbx+38h]
0x180018853  mov     rdx, [rbp+var_40]
0x180018857  mov     [rsp+80h+var_50], rdx
0x18001885c  mov     [rsp+80h+var_58], edi
0x180018860  mov     [rsp+80h+var_60], esi
0x180018864  xor     r8d, r8d
0x180018867  mov     rdx, [rbx+10h]
0x18001886b  mov     rax, [rax+250h]
0x180018872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018877  mov     [rbx+18h], rax
0x18001887b  test    rax, rax
0x18001887e  jz      short loc_18001889A
0x180018880  mov     rax, [rbx+8]
0x180018884  mov     rcx, [rax]
0x180018887  mov     [rbx+28h], rcx
0x18001888b  lea     rcx, [rbp+var_40]; this
0x18001888f  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x180018894  nop
0x180018895  jmp     loc_1800187B7
0x18001889a  lea     rcx, [rbp+var_40]; this
0x18001889e  call    ?Close@CObjectName@@QEAAXXZ; CObjectName::Close(void)
0x1800188a3  nop
0x1800188a4  xor     eax, eax
0x1800188a6  mov     rcx, [rbp+var_8]
0x1800188aa  xor     rcx, rsp; StackCookie
0x1800188ad  call    __security_check_cookie
0x1800188b2  mov     rbx, [rsp+80h+arg_10]
0x1800188ba  add     rsp, 80h
0x1800188c1  pop     rdi
0x1800188c2  pop     rsi
0x1800188c3  pop     rbp
0x1800188c4  retn
```
