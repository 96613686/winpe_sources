# CRegEventProvider::Initialize(ushort *,long,ushort *,ushort *,IWbemServices *,IWbemContext *,IWbemProviderInitSink *)

- ea: `0x18000a490`
- end: `0x18000a5e5`
- name: `?Initialize@CRegEventProvider@@UEAAJPEAGJ00PEAUIWbemServices@@PEAUIWbemContext@@PEAUIWbemProviderInitSink@@@Z`
- size: `341`
- prototype: `__int64 __fastcall(CRegEventProvider *this, unsigned __int16 *, __int64, unsigned __int16 *, unsigned __int16 *, struct IWbemServices *, struct IWbemContext *, struct IWbemProviderInitSink *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task`

## callees

- `0x18000a490`
- `0x180014350`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18000a5a0`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18000a5a0`

## string_xrefs

- `0x18000a530`: `RegistryValueChangeEvent`
- `0x18000a57d`: `RegistryTreeChangeEvent`
- `0x18000a4c9`: `RegistryKeyChangeEvent`

## pseudocode

```c
__int64 __fastcall CRegEventProvider::Initialize(
        CRegEventProvider *this,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IWbemServices *a6,
        struct IWbemContext *a7,
        struct IWbemProviderInitSink *a8)
{
  int v9; // eax
  signed int v10; // ebx
  HANDLE SemaphoreW; // rax

  v9 = ((__int64 (__fastcall *)(struct IWbemServices *, const unsigned __int16 *, _QWORD, struct IWbemContext *, char *, _QWORD))a6->lpVtbl->GetObjectA)(
         a6,
         L"RegistryKeyChangeEvent",
         0,
         a7,
         (char *)this + 16,
         0);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(struct IWbemServices *, const wchar_t *, _QWORD, struct IWbemContext *, char *, _QWORD))a6->lpVtbl->GetObjectA)(
            a6,
            L"RegistryValueChangeEvent",
            0,
            a7,
            (char *)this + 24,
            0);
    if ( v10 >= 0 )
    {
      v10 = ((__int64 (__fastcall *)(struct IWbemServices *, const unsigned __int16 *, _QWORD, struct IWbemContext *, char *, _QWORD))a6->lpVtbl->GetObjectA)(
              a6,
              L"RegistryTreeChangeEvent",
              0,
              a7,
              (char *)this + 32,
              0);
      if ( v10 >= 0 )
      {
        SemaphoreW = CreateSemaphoreW(0, 0, 0x7FFFFFFF, 0);
        *((_QWORD *)this + 25) = SemaphoreW;
        v10 = SemaphoreW == 0 ? 0x80041006 : 0;
      }
    }
  }
  else if ( v9 == -1
         && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && !*((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2));
  }
  ((void (__fastcall *)(struct IWbemProviderInitSink *, _QWORD, _QWORD))a8->lpVtbl->SetStatus)(a8, (unsigned int)v10, 0);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a490  mov     r11, rsp
0x18000a493  mov     [r11+8], rbx
0x18000a497  mov     [r11+10h], rsi
0x18000a49b  push    rdi
0x18000a49c  sub     rsp, 40h
0x18000a4a0  mov     rdi, [rsp+48h+arg_28]
0x18000a4a5  lea     rdx, [rcx+10h]
0x18000a4a9  mov     r9, [rsp+48h+arg_30]
0x18000a4b1  mov     rsi, rcx
0x18000a4b4  mov     qword ptr [r11-20h], 0
0x18000a4bc  xor     r8d, r8d
0x18000a4bf  mov     [r11-28h], rdx
0x18000a4c3  mov     rcx, rdi
0x18000a4c6  mov     rax, [rdi]
0x18000a4c9  lea     rdx, aRegistrykeycha; "RegistryKeyChangeEvent"
0x18000a4d0  mov     rax, [rax+30h]
0x18000a4d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4d9  mov     ebx, eax
0x18000a4db  test    eax, eax
0x18000a4dd  jns     short loc_18000A521
0x18000a4df  cmp     eax, 0FFFFFFFFh
0x18000a4e2  jnz     loc_18000A5BA
0x18000a4e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4ef  lea     rax, WPP_GLOBAL_Control
0x18000a4f6  cmp     rcx, rax
0x18000a4f9  jz      loc_18000A5BA
0x18000a4ff  test    byte ptr [rcx+1Ch], 8
0x18000a503  jz      loc_18000A5BA
0x18000a509  cmp     byte ptr [rcx+19h], 0
0x18000a50d  jnz     loc_18000A5BA
0x18000a513  mov     rcx, [rcx+10h]
0x18000a517  call    WPP_SF_
0x18000a51c  jmp     loc_18000A5BA
0x18000a521  mov     rax, [rdi]
0x18000a524  lea     rcx, [rsi+18h]
0x18000a528  mov     r9, [rsp+48h+arg_30]
0x18000a530  lea     rdx, aRegistryvaluec; "RegistryValueChangeEvent"
0x18000a537  mov     [rsp+48h+var_20], 0
0x18000a540  xor     r8d, r8d
0x18000a543  mov     [rsp+48h+var_28], rcx
0x18000a548  mov     rcx, rdi
0x18000a54b  mov     rax, [rax+30h]
0x18000a54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a554  mov     ebx, eax
0x18000a556  test    eax, eax
0x18000a558  js      short loc_18000A5BA
0x18000a55a  mov     rax, [rdi]
0x18000a55d  lea     rdx, [rsi+20h]
0x18000a561  mov     r9, [rsp+48h+arg_30]
0x18000a569  xor     r8d, r8d
0x18000a56c  mov     [rsp+48h+var_20], 0
0x18000a575  mov     rcx, rdi
0x18000a578  mov     [rsp+48h+var_28], rdx
0x18000a57d  lea     rdx, aRegistrytreech; "RegistryTreeChangeEvent"
0x18000a584  mov     rax, [rax+30h]
0x18000a588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a58d  mov     ebx, eax
0x18000a58f  test    eax, eax
0x18000a591  js      short loc_18000A5BA
0x18000a593  xor     r9d, r9d; lpName
0x18000a596  xor     edx, edx; lInitialCount
0x18000a598  xor     ecx, ecx; lpSemaphoreAttributes
0x18000a59a  mov     r8d, 7FFFFFFFh; lMaximumCount
0x18000a5a0  call    cs:__imp_CreateSemaphoreW
0x18000a5a6  mov     [rsi+0C8h], rax
0x18000a5ad  neg     rax
0x18000a5b0  sbb     ebx, ebx
0x18000a5b2  not     ebx
0x18000a5b4  and     ebx, 80041006h
0x18000a5ba  mov     rcx, [rsp+48h+arg_38]
0x18000a5c2  xor     r8d, r8d
0x18000a5c5  mov     edx, ebx
0x18000a5c7  mov     rax, [rcx]
0x18000a5ca  mov     rax, [rax+18h]
0x18000a5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5d3  mov     rsi, [rsp+48h+arg_8]
0x18000a5d8  mov     eax, ebx
0x18000a5da  mov     rbx, [rsp+48h+arg_0]
0x18000a5df  add     rsp, 40h
0x18000a5e3  pop     rdi
0x18000a5e4  retn
```
