# Microsoft::Windows::Performance::CEventTraceReloggerFactory::CreateEventTraceRelogger(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *,IUnknown *,_GUID const &,void * *)

- ea: `0x18000ac30`
- end: `0x18000acf3`
- name: `?CreateEventTraceRelogger@CEventTraceReloggerFactory@Performance@Windows@Microsoft@@UEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@PEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventTraceReloggerFactory *__hidden this, unsigned int, const unsigned __int16 *const *, const unsigned __int16 *, struct Microsoft::Windows::Performance::IEventTraceExtender *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ac30`
- `0x18000afd0`
- `0x18000bc6c`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventTraceReloggerFactory::CreateEventTraceRelogger(
        Microsoft::Windows::Performance::CEventTraceReloggerFactory *this,
        unsigned int a2,
        const unsigned __int16 *const *a3,
        const unsigned __int16 *a4,
        struct Microsoft::Windows::Performance::IEventTraceExtender *a5,
        struct IUnknown *a6,
        const struct _GUID *a7,
        void **a8)
{
  int Instance; // edi
  __int64 v13; // rbx
  _QWORD v14[7]; // [rsp+30h] [rbp-38h] BYREF

  if ( a2 && !a3 || !a4 )
    return 2147500035LL;
  v14[0] = 0;
  Instance = ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance((char *)a6, v14);
  if ( Instance >= 0 )
  {
    v13 = v14[0];
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v14[0] + 8LL))(v14[0]);
    Instance = Microsoft::Windows::Performance::CEventTraceRelogger::Init(
                 (Microsoft::Windows::Performance::CEventTraceRelogger *)(v13 + 16),
                 a2,
                 a3,
                 a4,
                 a5);
    if ( Instance >= 0 )
      Instance = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v13)(v13, a7, a8);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000ac30  push    rbx
0x18000ac32  push    rbp
0x18000ac33  push    rsi
0x18000ac34  push    rdi
0x18000ac35  push    r14
0x18000ac37  sub     rsp, 40h
0x18000ac3b  mov     rsi, r9
0x18000ac3e  mov     rbp, r8
0x18000ac41  mov     r14d, edx
0x18000ac44  test    edx, edx
0x18000ac46  jz      short loc_18000AC4D
0x18000ac48  test    r8, r8
0x18000ac4b  jz      short loc_18000AC52
0x18000ac4d  test    rsi, rsi
0x18000ac50  jnz     short loc_18000AC5C
0x18000ac52  mov     eax, 80004003h
0x18000ac57  jmp     loc_18000ACE7
0x18000ac5c  mov     rcx, [rsp+68h+arg_28]
0x18000ac64  lea     rdx, [rsp+68h+var_38]
0x18000ac69  mov     [rsp+68h+var_38], 0
0x18000ac72  call    ?CreateInstance@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@SAJPEAUIUnknown@@PEAPEAV12@@Z; ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::CreateInstance(IUnknown *,ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger> * *)
0x18000ac77  mov     edi, eax
0x18000ac79  test    eax, eax
0x18000ac7b  js      short loc_18000ACE5
0x18000ac7d  mov     rbx, [rsp+68h+var_38]
0x18000ac82  mov     rcx, rbx
0x18000ac85  mov     rax, [rbx]
0x18000ac88  mov     rax, [rax+8]
0x18000ac8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac91  mov     rax, [rsp+68h+arg_20]
0x18000ac99  lea     rcx, [rbx+10h]; this
0x18000ac9d  mov     r9, rsi; unsigned __int16 *
0x18000aca0  mov     [rsp+68h+var_48], rax; struct Microsoft::Windows::Performance::IEventTraceExtender *
0x18000aca5  mov     r8, rbp; unsigned __int16 **
0x18000aca8  mov     edx, r14d; unsigned int
0x18000acab  call    ?Init@CEventTraceRelogger@Performance@Windows@Microsoft@@QEAAJKPEBQEBGPEBGPEAUIEventTraceExtender@234@@Z; Microsoft::Windows::Performance::CEventTraceRelogger::Init(ulong,ushort const * const *,ushort const *,Microsoft::Windows::Performance::IEventTraceExtender *)
0x18000acb0  mov     edi, eax
0x18000acb2  test    eax, eax
0x18000acb4  js      short loc_18000ACD6
0x18000acb6  mov     rax, [rbx]
0x18000acb9  mov     rcx, rbx
0x18000acbc  mov     r8, [rsp+68h+arg_38]
0x18000acc4  mov     rdx, [rsp+68h+arg_30]
0x18000accc  mov     rax, [rax]
0x18000accf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acd4  mov     edi, eax
0x18000acd6  mov     rax, [rbx]
0x18000acd9  mov     rcx, rbx
0x18000acdc  mov     rax, [rax+10h]
0x18000ace0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ace5  mov     eax, edi
0x18000ace7  add     rsp, 40h
0x18000aceb  pop     r14
0x18000aced  pop     rdi
0x18000acee  pop     rsi
0x18000acef  pop     rbp
0x18000acf0  pop     rbx
0x18000acf1  retn
```
