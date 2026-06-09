# Wsp::Health::ResClient::GetAction(wchar_t const *,void (*)(_HEALTH_ACTION_CLIENT *,void *),void *)

- ea: `0x180078938`
- end: `0x180078a5a`
- name: `?GetAction@ResClient@Health@Wsp@@QEAAJPEB_WP6AXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z2@Z`
- size: `290`
- prototype: `__int64 __fastcall(Wsp::Health::ResClient *__hidden this, PCNZWCH lpString1, void (*)(struct _HEALTH_ACTION_CLIENT *, void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180077964`

## callees

- `0x180077704`
- `0x180078938`
- `0x180078bcc`
- `0x180079eac`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800789a5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800789a5`

## pseudocode

```c
__int64 __fastcall Wsp::Health::ResClient::GetAction(
        Wsp::Health::ResClient *this,
        PCNZWCH lpString1,
        void (*a3)(struct _HEALTH_ACTION_CLIENT *, void *),
        void *a4)
{
  signed int Connection; // ebx
  PCNZWCH v9; // rbp
  Wsp::Health::ResClient *v10; // rcx
  Wsp::Health::ResClient *v11; // rcx
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF
  void (*v13)(struct _HEALTH_ACTION_CLIENT *, void *); // [rsp+60h] [rbp+18h] BYREF

  v13 = a3;
  if ( !*((_QWORD *)this + 11) )
    return 2147943557LL;
  v12 = 0;
  if ( (int)Wsp::Health::ResClient::GetConnection(this) >= 0 )
  {
    v9 = 0;
    if ( CompareStringW(0x400u, 1u, lpString1, -1, &String1, -1) != 2 )
      v9 = lpString1;
    LODWORD(v13) = (*((__int64 (__fastcall **)(_QWORD, PCNZWCH, void (__fastcall *)(Wsp::Health *__hidden, struct _HEALTH_ACTION_CLIENT *, void *), void *))this
                    + 11))(
                     *(_QWORD *)(v12 + 16),
                     v9,
                     Wsp::Health::HealthGetActionsApiCallback,
                     a4);
    Connection = (int)v13;
    if ( !Wsp::Health::ResClient::ValidateOperation(v10, (unsigned int *)&v13) )
      goto LABEL_11;
    Connection = Wsp::Health::ResClient::GetConnection(this);
    if ( Connection < 0 )
      goto LABEL_13;
    LODWORD(v13) = (*((__int64 (__fastcall **)(_QWORD, PCNZWCH, void (__fastcall *)(Wsp::Health *__hidden, struct _HEALTH_ACTION_CLIENT *, void *), void *))this
                    + 11))(
                     *(_QWORD *)(v12 + 16),
                     v9,
                     Wsp::Health::HealthGetActionsApiCallback,
                     a4);
    Connection = (int)v13;
    if ( Wsp::Health::ResClient::ValidateOperation(v11, (unsigned int *)&v13) )
    {
      LOWORD(Connection) = 110;
    }
    else
    {
LABEL_11:
      if ( Connection <= 0 )
        goto LABEL_13;
    }
    Connection = (unsigned __int16)Connection | 0x80070000;
    goto LABEL_13;
  }
  Connection = -2147024786;
LABEL_13:
  Wsp::Health::RefCounted<Wsp::Health::CHealthConnection>::~RefCounted<Wsp::Health::CHealthConnection>(&v12);
  return (unsigned int)Connection;
}

```

## disassembly

```asm
0x180078938  mov     [rsp+arg_8], rbx
0x18007893d  mov     [rsp+arg_10], r8
0x180078942  push    rbp
0x180078943  push    rsi
0x180078944  push    rdi
0x180078945  sub     rsp, 30h
0x180078949  cmp     qword ptr [rcx+58h], 0
0x18007894e  mov     rsi, r9
0x180078951  mov     rbx, rdx
0x180078954  mov     rdi, rcx
0x180078957  jnz     short loc_180078963
0x180078959  mov     eax, 80070485h
0x18007895e  jmp     loc_180078A4D
0x180078963  lea     rdx, [rsp+48h+arg_0]
0x180078968  mov     [rsp+48h+arg_0], 0
0x180078971  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x180078976  test    eax, eax
0x180078978  jns     short loc_180078984
0x18007897a  mov     ebx, 8007006Eh
0x18007897f  jmp     loc_180078A41
0x180078984  or      r9d, 0FFFFFFFFh; cchCount1
0x180078988  lea     rax, String1
0x18007898f  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x180078994  mov     r8, rbx; lpString1
0x180078997  mov     ecx, 400h; Locale
0x18007899c  mov     [rsp+48h+lpString2], rax; lpString2
0x1800789a1  lea     edx, [r9+2]; dwCmpFlags
0x1800789a5  call    cs:__imp_CompareStringW
0x1800789ab  mov     rcx, [rsp+48h+arg_0]
0x1800789b0  lea     r8, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x1800789b7  xor     ebp, ebp
0x1800789b9  mov     r9, rsi
0x1800789bc  cmp     eax, 2
0x1800789bf  mov     rax, [rdi+58h]
0x1800789c3  mov     rcx, [rcx+10h]
0x1800789c7  cmovnz  rbp, rbx
0x1800789cb  mov     rdx, rbp
0x1800789ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800789d3  lea     rdx, [rsp+48h+arg_10]; unsigned int *
0x1800789d8  mov     dword ptr [rsp+48h+arg_10], eax
0x1800789dc  mov     ebx, eax
0x1800789de  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x1800789e3  test    al, al
0x1800789e5  jz      short loc_180078A34
0x1800789e7  lea     rdx, [rsp+48h+arg_0]
0x1800789ec  mov     rcx, rdi; void *
0x1800789ef  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x1800789f4  mov     ebx, eax
0x1800789f6  test    eax, eax
0x1800789f8  js      short loc_180078A41
0x1800789fa  mov     rcx, [rsp+48h+arg_0]
0x1800789ff  lea     r8, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x180078a06  mov     rax, [rdi+58h]
0x180078a0a  mov     r9, rsi
0x180078a0d  mov     rdx, rbp
0x180078a10  mov     rcx, [rcx+10h]
0x180078a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078a19  lea     rdx, [rsp+48h+arg_10]; unsigned int *
0x180078a1e  mov     dword ptr [rsp+48h+arg_10], eax
0x180078a22  mov     ebx, eax
0x180078a24  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x180078a29  test    al, al
0x180078a2b  jz      short loc_180078A34
0x180078a2d  mov     ebx, 6Eh ; 'n'
0x180078a32  jmp     short loc_180078A38
0x180078a34  test    ebx, ebx
0x180078a36  jle     short loc_180078A41
0x180078a38  movzx   ebx, bx
0x180078a3b  or      ebx, 80070000h
0x180078a41  lea     rcx, [rsp+48h+arg_0]
0x180078a46  call    ??1?$RefCounted@VCHealthConnection@Health@Wsp@@@Health@Wsp@@QEAA@XZ; Wsp::Health::RefCounted<Wsp::Health::CHealthConnection>::~RefCounted<Wsp::Health::CHealthConnection>(void)
0x180078a4b  mov     eax, ebx
0x180078a4d  mov     rbx, [rsp+48h+arg_8]
0x180078a52  add     rsp, 30h
0x180078a56  pop     rdi
0x180078a57  pop     rsi
0x180078a58  pop     rbp
0x180078a59  retn
```
