# IHVHelper::IHVHlpInitialize(void)

- ea: `0x180011224`
- end: `0x180011300`
- name: `?IHVHlpInitialize@IHVHelper@@QEAAJXZ`
- size: `220`
- prototype: `__int64 __fastcall(IHVHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000fe78`

## callees

- `0x180001d98`
- `0x180010b38`
- `0x180011224`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180011252`
- `ole32!CoCreateInstance` at `0x180011252`

## pseudocode

```c
__int64 __fastcall IHVHelper::IHVHlpInitialize(const IID *this)
{
  HRESULT Instance; // esi
  const IID *v3; // rdi
  void *v4; // rax
  void *v5; // rax
  void *v6; // rax

  Instance = 0;
  if ( *(_DWORD *)&this[3].Data2 )
  {
    v3 = this + 1;
    Instance = CoCreateInstance(this, 0, 1u, &IID_IDot11ExtUI, (LPVOID *)&this[1]);
    if ( Instance >= 0 )
    {
      v4 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v4 )
        v4 = (void *)IHVExtHelper::IHVExtHelper(v4, 0, *(_QWORD *)&v3->Data1, 0);
      *(_QWORD *)this[1].Data4 = v4;
      v5 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v5 )
        v5 = (void *)IHVExtHelper::IHVExtHelper(v5, 1, *(_QWORD *)&v3->Data1, 2147549184LL);
      *(_QWORD *)&this[2].Data1 = v5;
      v6 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v6 )
        v6 = (void *)IHVExtHelper::IHVExtHelper(v6, 2, *(_QWORD *)&v3->Data1, 0x80000000LL);
      *(_QWORD *)this[2].Data4 = v6;
    }
    else
    {
      *(_QWORD *)&v3->Data1 = 0;
    }
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180011224  push    rbx
0x180011226  push    rsi
0x180011227  push    rdi
0x180011228  push    r14
0x18001122a  sub     rsp, 38h
0x18001122e  xor     esi, esi
0x180011230  mov     rbx, rcx
0x180011233  cmp     [rcx+34h], esi
0x180011236  jz      loc_1800112F4
0x18001123c  lea     rdi, [rcx+10h]
0x180011240  xor     edx, edx; pUnkOuter
0x180011242  lea     r9, IID_IDot11ExtUI; riid
0x180011249  mov     [rsp+58h+ppv], rdi; ppv
0x18001124e  lea     r8d, [rsi+1]; dwClsContext
0x180011252  call    cs:__imp_CoCreateInstance
0x180011258  mov     esi, eax
0x18001125a  test    eax, eax
0x18001125c  jns     short loc_18001126A
0x18001125e  mov     qword ptr [rdi], 0
0x180011265  jmp     loc_1800112F4
0x18001126a  mov     r14d, 28h ; '('
0x180011270  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180011277  mov     ecx, r14d; unsigned __int64
0x18001127a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001127f  test    rax, rax
0x180011282  jz      short loc_180011294
0x180011284  mov     r8, [rdi]
0x180011287  xor     r9d, r9d
0x18001128a  xor     edx, edx
0x18001128c  mov     rcx, rax
0x18001128f  call    ??0IHVExtHelper@@QEAA@W4_DOT11_EXT_UI_PROPERTY_TYPE@@PEAUIDot11ExtUI@@K@Z; IHVExtHelper::IHVExtHelper(_DOT11_EXT_UI_PROPERTY_TYPE,IDot11ExtUI *,ulong)
0x180011294  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001129b  mov     [rbx+18h], rax
0x18001129f  mov     rcx, r14; unsigned __int64
0x1800112a2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800112a7  test    rax, rax
0x1800112aa  jz      short loc_1800112C2
0x1800112ac  mov     r8, [rdi]
0x1800112af  mov     r9d, 80010000h
0x1800112b5  mov     edx, 1
0x1800112ba  mov     rcx, rax
0x1800112bd  call    ??0IHVExtHelper@@QEAA@W4_DOT11_EXT_UI_PROPERTY_TYPE@@PEAUIDot11ExtUI@@K@Z; IHVExtHelper::IHVExtHelper(_DOT11_EXT_UI_PROPERTY_TYPE,IDot11ExtUI *,ulong)
0x1800112c2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800112c9  mov     [rbx+20h], rax
0x1800112cd  mov     rcx, r14; unsigned __int64
0x1800112d0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800112d5  test    rax, rax
0x1800112d8  jz      short loc_1800112F0
0x1800112da  mov     r8, [rdi]
0x1800112dd  mov     r9d, 80000000h
0x1800112e3  mov     edx, 2
0x1800112e8  mov     rcx, rax
0x1800112eb  call    ??0IHVExtHelper@@QEAA@W4_DOT11_EXT_UI_PROPERTY_TYPE@@PEAUIDot11ExtUI@@K@Z; IHVExtHelper::IHVExtHelper(_DOT11_EXT_UI_PROPERTY_TYPE,IDot11ExtUI *,ulong)
0x1800112f0  mov     [rbx+28h], rax
0x1800112f4  mov     eax, esi
0x1800112f6  add     rsp, 38h
0x1800112fa  pop     r14
0x1800112fc  pop     rdi
0x1800112fd  pop     rsi
0x1800112fe  pop     rbx
0x1800112ff  retn
```
