# DllGetClassObject

- ea: `0x18000abb0`
- end: `0x18000ac70`
- name: `DllGetClassObject`
- size: `192`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008aec`
- `0x18000abb0`
- `0x18000ac98`
- `0x18001e010`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 v5; // rax
  __int64 v6; // rax
  HRESULT v7; // ebx
  WCMClassFactory *v8; // rax
  WCMClassFactory *v9; // rax
  WCMClassFactory *v10; // rdi

  *ppv = 0;
  v5 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&GUID_a166cf69_93b2_49fb_8143_dcefd4bf8ba9.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&GUID_a166cf69_93b2_49fb_8143_dcefd4bf8ba9.Data1 )
    v5 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)GUID_a166cf69_93b2_49fb_8143_dcefd4bf8ba9.Data4;
  if ( !v5 )
    goto LABEL_8;
  v6 = *(_QWORD *)&rclsid->Data1 - *(_QWORD *)&GUID_9c8db22b_8ddc_471c_9628_48847514b424.Data1;
  if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&GUID_9c8db22b_8ddc_471c_9628_48847514b424.Data1 )
    v6 = *(_QWORD *)rclsid->Data4 - *(_QWORD *)GUID_9c8db22b_8ddc_471c_9628_48847514b424.Data4;
  if ( v6 )
    return -2147221164;
LABEL_8:
  v8 = (WCMClassFactory *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v8 )
    return -2147024882;
  v9 = WCMClassFactory::WCMClassFactory(v8);
  v10 = v9;
  if ( !v9 )
    return -2147024882;
  v7 = (**(__int64 (__fastcall ***)(WCMClassFactory *, const IID *const, LPVOID *))v9)(v9, riid, ppv);
  (*(void (__fastcall **)(WCMClassFactory *))(*(_QWORD *)v10 + 16LL))(v10);
  return v7;
}

```

## disassembly

```asm
0x18000abb0  mov     [rsp+arg_0], rbx
0x18000abb5  mov     [rsp+arg_8], rsi
0x18000abba  push    rdi
0x18000abbb  sub     rsp, 20h
0x18000abbf  mov     qword ptr [r8], 0
0x18000abc6  mov     rbx, r8
0x18000abc9  mov     rax, [rcx]
0x18000abcc  mov     rsi, rdx
0x18000abcf  sub     rax, qword ptr cs:_GUID_a166cf69_93b2_49fb_8143_dcefd4bf8ba9.Data1
0x18000abd6  jnz     short loc_18000ABE3
0x18000abd8  mov     rax, [rcx+8]
0x18000abdc  sub     rax, qword ptr cs:_GUID_a166cf69_93b2_49fb_8143_dcefd4bf8ba9.Data4
0x18000abe3  test    rax, rax
0x18000abe6  jz      short loc_18000AC0B
0x18000abe8  mov     rax, [rcx]
0x18000abeb  sub     rax, qword ptr cs:_GUID_9c8db22b_8ddc_471c_9628_48847514b424.Data1
0x18000abf2  jnz     short loc_18000ABFF
0x18000abf4  mov     rax, [rcx+8]
0x18000abf8  sub     rax, qword ptr cs:_GUID_9c8db22b_8ddc_471c_9628_48847514b424.Data4
0x18000abff  test    rax, rax
0x18000ac02  jz      short loc_18000AC0B
0x18000ac04  mov     ebx, 80040154h
0x18000ac09  jmp     short loc_18000AC5D
0x18000ac0b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ac12  mov     ecx, 10h; unsigned __int64
0x18000ac17  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ac1c  test    rax, rax
0x18000ac1f  jz      short loc_18000AC58
0x18000ac21  mov     rcx, rax; this
0x18000ac24  call    ??0WCMClassFactory@@QEAA@XZ; WCMClassFactory::WCMClassFactory(void)
0x18000ac29  mov     rdi, rax
0x18000ac2c  test    rax, rax
0x18000ac2f  jz      short loc_18000AC58
0x18000ac31  mov     rax, [rax]
0x18000ac34  mov     r8, rbx
0x18000ac37  mov     rdx, rsi
0x18000ac3a  mov     rcx, rdi
0x18000ac3d  mov     rax, [rax]
0x18000ac40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac45  mov     rcx, [rdi]
0x18000ac48  mov     ebx, eax
0x18000ac4a  mov     rax, [rcx+10h]
0x18000ac4e  mov     rcx, rdi
0x18000ac51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac56  jmp     short loc_18000AC5D
0x18000ac58  mov     ebx, 8007000Eh
0x18000ac5d  mov     rsi, [rsp+28h+arg_8]
0x18000ac62  mov     eax, ebx
0x18000ac64  mov     rbx, [rsp+28h+arg_0]
0x18000ac69  add     rsp, 20h
0x18000ac6d  pop     rdi
0x18000ac6e  retn
```
