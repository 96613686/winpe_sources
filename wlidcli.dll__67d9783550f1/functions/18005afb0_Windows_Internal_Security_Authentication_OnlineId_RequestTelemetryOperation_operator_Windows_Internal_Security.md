# Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::operator=(Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation &&)

- ea: `0x18005afb0`
- end: `0x18005b039`
- name: `??4RequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@QEAAAEAV012345@$$QEAV012345@@Z`
- size: `137`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18005ad60`

## callees

- `0x18005afb0`
- `0x18005b0d4`
- `0x18005b190`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005afd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005afd5`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::operator=(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rbx
  __int64 *v5; // r14
  __int64 *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx

  if ( a2 != a1 )
  {
    v4 = *(_QWORD *)(a2 + 24);
    *(_QWORD *)(a2 + 24) = 0;
    WindowsDeleteString(*(HSTRING *)(a1 + 24));
    *(_QWORD *)(a1 + 24) = v4;
    v5 = (__int64 *)(a2 + 32);
    v6 = (__int64 *)(a1 + 32);
    *(_QWORD *)a1 = *(_QWORD *)a2;
    *(_QWORD *)(a1 + 8) = *(_QWORD *)(a2 + 8);
    *(_BYTE *)(a1 + 16) = *(_BYTE *)(a2 + 16);
    if ( a1 + 32 != a2 + 32 )
    {
      std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::clear(a1 + 32);
      v7 = *v6;
      *v6 = *v5;
      v8 = *(_QWORD *)(a2 + 40);
      *v5 = v7;
      v9 = *(_QWORD *)(a1 + 40);
      *(_QWORD *)(a1 + 40) = v8;
      *(_QWORD *)(a2 + 40) = v9;
    }
    Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::Reset((Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *)a2);
  }
  return a1;
}

```

## disassembly

```asm
0x18005afb0  push    rbx
0x18005afb2  push    rsi
0x18005afb3  push    rdi
0x18005afb4  push    r14
0x18005afb6  sub     rsp, 28h
0x18005afba  mov     rsi, rdx
0x18005afbd  mov     rdi, rcx
0x18005afc0  cmp     rdx, rcx
0x18005afc3  jz      short loc_18005B02C
0x18005afc5  mov     rbx, [rdx+18h]
0x18005afc9  mov     qword ptr [rdx+18h], 0
0x18005afd1  mov     rcx, [rcx+18h]; string
0x18005afd5  call    cs:__imp_WindowsDeleteString
0x18005afdb  mov     [rdi+18h], rbx
0x18005afdf  lea     r14, [rsi+20h]
0x18005afe3  mov     rax, [rsi]
0x18005afe6  lea     rbx, [rdi+20h]
0x18005afea  mov     [rdi], rax
0x18005afed  mov     rax, [rsi+8]
0x18005aff1  mov     [rdi+8], rax
0x18005aff5  mov     al, [rsi+10h]
0x18005aff8  mov     [rdi+10h], al
0x18005affb  cmp     rbx, r14
0x18005affe  jz      short loc_18005B024
0x18005b000  mov     rcx, rbx
0x18005b003  call    ?clear@?$list@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@V?$allocator@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAXXZ; std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::clear(void)
0x18005b008  mov     rax, [r14]
0x18005b00b  mov     rcx, [rbx]
0x18005b00e  mov     [rbx], rax
0x18005b011  mov     rax, [r14+8]
0x18005b015  mov     [r14], rcx
0x18005b018  mov     rcx, [rbx+8]
0x18005b01c  mov     [rbx+8], rax
0x18005b020  mov     [r14+8], rcx
0x18005b024  mov     rcx, rsi; this
0x18005b027  call    ?Reset@RequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAAXXZ; Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::Reset(void)
0x18005b02c  mov     rax, rdi
0x18005b02f  add     rsp, 28h
0x18005b033  pop     r14
0x18005b035  pop     rdi
0x18005b036  pop     rsi
0x18005b037  pop     rbx
0x18005b038  retn
```
