# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IEventLogger,Microsoft::WRL::FtmBase>::GetIids(ulong *,_GUID * *)

- ea: `0x140038bb0`
- end: `0x140038c16`
- name: `?GetIids@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIEventLogger@SmartScreen@Security@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140038814`
- `0x140038bb0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038bd2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140038bd2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Security::SmartScreen::IEventLogger,Microsoft::WRL::FtmBase>::GetIids(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  LPVOID v6; // r8
  __int64 result; // rax
  __int64 v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v6 = CoTaskMemAlloc(0x20u);
  if ( !v6 )
    return 2147942414LL;
  v9 = 0;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IEventLogger,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v5,
    &v9,
    v6);
  *a2 = 2;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x140038bb0  mov     [rsp+arg_0], rbx
0x140038bb5  push    rdi
0x140038bb6  sub     rsp, 20h
0x140038bba  mov     qword ptr [r8], 0
0x140038bc1  mov     ecx, 20h ; ' '; cb
0x140038bc6  mov     dword ptr [rdx], 0
0x140038bcc  mov     rbx, r8
0x140038bcf  mov     rdi, rdx
0x140038bd2  call    cs:__imp_CoTaskMemAlloc
0x140038bd9  nop     dword ptr [rax+rax+00h]
0x140038bde  mov     r8, rax
0x140038be1  test    rax, rax
0x140038be4  jnz     short loc_140038BED
0x140038be6  mov     eax, 8007000Eh
0x140038beb  jmp     short loc_140038C0A
0x140038bed  lea     rdx, [rsp+28h+arg_8]
0x140038bf2  mov     [rsp+28h+arg_8], 0
0x140038bfa  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$0A@UIEventLogger@SmartScreen@Security@Internal@Windows@@UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,0,Windows::Internal::Security::SmartScreen::IEventLogger,IWeakReferenceSource,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x140038bff  mov     dword ptr [rdi], 2
0x140038c05  xor     eax, eax
0x140038c07  mov     [rbx], r8
0x140038c0a  mov     rbx, [rsp+28h+arg_0]
0x140038c0f  add     rsp, 20h
0x140038c13  pop     rdi
0x140038c14  retn
```
