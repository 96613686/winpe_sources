# ATL::CComCreator<ATL::CComObject<CPXWizardRegistration>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x1800042dc`
- end: `0x1800043e0`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCPXWizardRegistration@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `260`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003e30`

## callees

- `0x1800011dc`
- `0x1800042dc`
- `0x180004a90`
- `0x180013010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CPXWizardRegistration>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  int v10; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = operator new(0x40u);
  v8 = v7;
  if ( v7 )
  {
    v7[2] = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    *((_BYTE *)v7 + 56) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CPXWizardRegistration>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
  }
  if ( v8 )
  {
    v9 = ATL::CComSafeDeleteCriticalSection::Init((ATL::CComSafeDeleteCriticalSection *)(v8 + 4));
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    v6 = 0;
    if ( v10 < 0 )
      v6 = v10;
    if ( v6 || (v6 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v8 + 96LL))(v8, 1);
  }
  return v6;
}

```

## disassembly

```asm
0x1800042dc  mov     [rsp+arg_10], r8
0x1800042e1  mov     [rsp+arg_8], rdx
0x1800042e6  mov     [rsp+arg_0], rcx
0x1800042eb  push    rbx
0x1800042ec  push    rsi
0x1800042ed  push    rdi
0x1800042ee  push    r14
0x1800042f0  sub     rsp, 28h
0x1800042f4  mov     rsi, r8
0x1800042f7  mov     r14, rdx
0x1800042fa  test    r8, r8
0x1800042fd  jnz     short loc_180004309
0x1800042ff  mov     eax, 80004003h
0x180004304  jmp     loc_1800043D6
0x180004309  mov     qword ptr [r8], 0
0x180004310  mov     edi, 8007000Eh
0x180004315  mov     dword ptr [rsp+48h+arg_0], edi
0x180004319  mov     [rsp+48h+arg_18], 0
0x180004322  mov     ecx, 40h ; '@'; Size
0x180004327  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000432c  mov     rbx, rax
0x18000432f  test    rbx, rbx
0x180004332  jz      short loc_18000436C
0x180004334  mov     dword ptr [rax+8], 0
0x18000433b  xorps   xmm0, xmm0
0x18000433e  xor     eax, eax
0x180004340  movups  xmmword ptr [rbx+10h], xmm0
0x180004344  movups  xmmword ptr [rbx+20h], xmm0
0x180004348  mov     [rbx+30h], rax
0x18000434c  mov     [rbx+38h], al
0x18000434f  lea     rax, ??_7?$CComObject@VCPXWizardRegistration@@@ATL@@6B@; const ATL::CComObject<CPXWizardRegistration>::`vftable'
0x180004356  mov     [rbx], rax
0x180004359  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004360  mov     rax, [rcx]
0x180004363  mov     rax, [rax+8]
0x180004367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000436c  mov     [rsp+48h+arg_18], rbx
0x180004371  jmp     short loc_180004386
0x180004373  mov     rsi, [rsp+48h+arg_10]
0x180004378  mov     r14, [rsp+48h+arg_8]
0x18000437d  mov     edi, dword ptr [rsp+48h+arg_0]
0x180004381  mov     rbx, [rsp+48h+arg_18]
0x180004386  test    rbx, rbx
0x180004389  jz      short loc_1800043D4
0x18000438b  lea     rcx, [rbx+10h]; this
0x18000438f  call    ?Init@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Init(void)
0x180004394  xor     ecx, ecx
0x180004396  test    eax, eax
0x180004398  cmovs   ecx, eax
0x18000439b  xor     edi, edi
0x18000439d  test    ecx, ecx
0x18000439f  cmovs   edi, ecx
0x1800043a2  test    edi, edi
0x1800043a4  jnz     short loc_1800043C0
0x1800043a6  mov     rax, [rbx]
0x1800043a9  mov     r8, rsi
0x1800043ac  mov     rdx, r14
0x1800043af  mov     rcx, rbx
0x1800043b2  mov     rax, [rax]
0x1800043b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ba  mov     edi, eax
0x1800043bc  test    eax, eax
0x1800043be  jz      short loc_1800043D4
0x1800043c0  mov     rdx, [rbx]
0x1800043c3  mov     rax, [rdx+60h]
0x1800043c7  mov     edx, 1
0x1800043cc  mov     rcx, rbx
0x1800043cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043d4  mov     eax, edi
0x1800043d6  add     rsp, 28h
0x1800043da  pop     r14
0x1800043dc  pop     rdi
0x1800043dd  pop     rsi
0x1800043de  pop     rbx
0x1800043df  retn
```
