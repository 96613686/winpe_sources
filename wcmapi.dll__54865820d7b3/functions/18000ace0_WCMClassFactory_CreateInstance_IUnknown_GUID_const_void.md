# WCMClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000ace0`
- end: `0x18000ade7`
- name: `?CreateInstance@WCMClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `263`
- prototype: `__int64 __fastcall(WCMClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180008aec`
- `0x18000ace0`
- `0x18000aec0`
- `0x1800172b0`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall WCMClassFactory::CreateInstance(
        WCMClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rax
  WcmConnectionSelectionManager *v8; // rax
  WcmConnectionSelectionManager *v9; // rax
  WcmConnectionSelectionManager *v10; // rdi
  __int64 v11; // rax
  WcmPolicyManager *v12; // rax

  *a4 = 0;
  if ( !a2 )
  {
    v7 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_d8f242cb_e6f3_4ce1_9ca2_555b6bf48f6e.Data1;
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_d8f242cb_e6f3_4ce1_9ca2_555b6bf48f6e.Data1 )
      v7 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_d8f242cb_e6f3_4ce1_9ca2_555b6bf48f6e.Data4;
    if ( v7 )
    {
      v11 = *(_QWORD *)&a3->Data1 - *(_QWORD *)&GUID_ba9f757d_4472_4cb8_a6f3_27f1d56f67f1.Data1;
      if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_ba9f757d_4472_4cb8_a6f3_27f1d56f67f1.Data1 )
        v11 = *(_QWORD *)a3->Data4 - *(_QWORD *)GUID_ba9f757d_4472_4cb8_a6f3_27f1d56f67f1.Data4;
      if ( v11 )
        return (unsigned int)-2147467262;
      v12 = (WcmPolicyManager *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v12 )
      {
        v9 = WcmPolicyManager::WcmPolicyManager(v12);
        v10 = v9;
        if ( v9 )
          goto LABEL_8;
      }
    }
    else
    {
      v8 = (WcmConnectionSelectionManager *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v8 )
      {
        v9 = WcmConnectionSelectionManager::WcmConnectionSelectionManager(v8);
        v10 = v9;
        if ( v9 )
        {
LABEL_8:
          v6 = (**(__int64 (__fastcall ***)(WcmConnectionSelectionManager *, const struct _GUID *, void **))v9)(
                 v10,
                 a3,
                 a4);
          (*(void (__fastcall **)(WcmConnectionSelectionManager *))(*(_QWORD *)v10 + 16LL))(v10);
          return v6;
        }
      }
    }
    return (unsigned int)-2147024882;
  }
  return (unsigned int)-2147221232;
}

```

## disassembly

```asm
0x18000ace0  mov     [rsp+arg_0], rbx
0x18000ace5  mov     [rsp+arg_10], rsi
0x18000acea  push    rdi
0x18000aceb  sub     rsp, 20h
0x18000acef  mov     qword ptr [r9], 0
0x18000acf6  mov     rsi, r9
0x18000acf9  mov     rbx, r8
0x18000acfc  test    rdx, rdx
0x18000acff  jz      short loc_18000AD0B
0x18000ad01  mov     ebx, 80040110h
0x18000ad06  jmp     loc_18000ADD4
0x18000ad0b  mov     rax, [r8]
0x18000ad0e  sub     rax, qword ptr cs:_GUID_d8f242cb_e6f3_4ce1_9ca2_555b6bf48f6e.Data1
0x18000ad15  jnz     short loc_18000AD22
0x18000ad17  mov     rax, [r8+8]
0x18000ad1b  sub     rax, qword ptr cs:_GUID_d8f242cb_e6f3_4ce1_9ca2_555b6bf48f6e.Data4
0x18000ad22  test    rax, rax
0x18000ad25  jnz     short loc_18000AD7B
0x18000ad27  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ad2e  lea     ecx, [rax+10h]; unsigned __int64
0x18000ad31  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ad36  mov     [rsp+28h+arg_8], rax
0x18000ad3b  test    rax, rax
0x18000ad3e  jz      loc_18000ADC8
0x18000ad44  mov     rcx, rax; this
0x18000ad47  call    ??0WcmConnectionSelectionManager@@QEAA@XZ; WcmConnectionSelectionManager::WcmConnectionSelectionManager(void)
0x18000ad4c  mov     rdi, rax
0x18000ad4f  test    rax, rax
0x18000ad52  jz      short loc_18000ADC8
0x18000ad54  mov     rax, [rax]
0x18000ad57  mov     rax, [rax]
0x18000ad5a  mov     rcx, rdi
0x18000ad5d  mov     rdx, rbx
0x18000ad60  mov     r8, rsi
0x18000ad63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad68  mov     rcx, [rdi]
0x18000ad6b  mov     ebx, eax
0x18000ad6d  mov     rax, [rcx+10h]
0x18000ad71  mov     rcx, rdi
0x18000ad74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad79  jmp     short loc_18000ADD4
0x18000ad7b  mov     rax, [r8]
0x18000ad7e  sub     rax, qword ptr cs:_GUID_ba9f757d_4472_4cb8_a6f3_27f1d56f67f1.Data1
0x18000ad85  jnz     short loc_18000AD92
0x18000ad87  mov     rax, [r8+8]
0x18000ad8b  sub     rax, qword ptr cs:_GUID_ba9f757d_4472_4cb8_a6f3_27f1d56f67f1.Data4
0x18000ad92  test    rax, rax
0x18000ad95  jnz     short loc_18000ADCF
0x18000ad97  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ad9e  lea     ecx, [rax+10h]; unsigned __int64
0x18000ada1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ada6  mov     [rsp+28h+arg_8], rax
0x18000adab  test    rax, rax
0x18000adae  jz      short loc_18000ADC8
0x18000adb0  mov     rcx, rax; this
0x18000adb3  call    ??0WcmPolicyManager@@QEAA@XZ; WcmPolicyManager::WcmPolicyManager(void)
0x18000adb8  mov     rdi, rax
0x18000adbb  test    rax, rax
0x18000adbe  jz      short loc_18000ADC8
0x18000adc0  mov     rcx, [rax]
0x18000adc3  mov     rax, [rcx]
0x18000adc6  jmp     short loc_18000AD5A
0x18000adc8  mov     ebx, 8007000Eh
0x18000adcd  jmp     short loc_18000ADD4
0x18000adcf  mov     ebx, 80004002h
0x18000add4  mov     rsi, [rsp+28h+arg_10]
0x18000add9  mov     eax, ebx
0x18000addb  mov     rbx, [rsp+28h+arg_0]
0x18000ade0  add     rsp, 20h
0x18000ade4  pop     rdi
0x18000ade5  retn
```
