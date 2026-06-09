# Wsp::Health::ResClient::GetAction(wchar_t const *,void (*)(_HEALTH_ACTION_CLIENT *,void *),void *)

- ea: `0x18007a8c8`
- end: `0x18007a9f1`
- name: `?GetAction@ResClient@Health@Wsp@@QEAAJPEB_WP6AXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z2@Z`
- size: `297`
- prototype: `__int64 __fastcall(Wsp::Health::ResClient *__hidden this, PCNZWCH lpString1, void (*)(struct _HEALTH_ACTION_CLIENT *, void *), void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180079828`

## callees

- `0x1800795b8`
- `0x18007a8c8`
- `0x18007ab70`
- `0x18007bfe4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007a935`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18007a935`

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
0x18007a8c8  mov     [rsp+arg_8], rbx
0x18007a8cd  mov     [rsp+arg_10], r8
0x18007a8d2  push    rbp
0x18007a8d3  push    rsi
0x18007a8d4  push    rdi
0x18007a8d5  sub     rsp, 30h
0x18007a8d9  cmp     qword ptr [rcx+58h], 0
0x18007a8de  mov     rsi, r9
0x18007a8e1  mov     rbx, rdx
0x18007a8e4  mov     rdi, rcx
0x18007a8e7  jnz     short loc_18007A8F3
0x18007a8e9  mov     eax, 80070485h
0x18007a8ee  jmp     loc_18007A9E3
0x18007a8f3  lea     rdx, [rsp+48h+arg_0]
0x18007a8f8  mov     [rsp+48h+arg_0], 0
0x18007a901  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x18007a906  test    eax, eax
0x18007a908  jns     short loc_18007A914
0x18007a90a  mov     ebx, 8007006Eh
0x18007a90f  jmp     loc_18007A9D7
0x18007a914  or      r9d, 0FFFFFFFFh; cchCount1
0x18007a918  lea     rax, String1
0x18007a91f  mov     [rsp+48h+cchCount2], r9d; cchCount2
0x18007a924  mov     r8, rbx; lpString1
0x18007a927  mov     ecx, 400h; Locale
0x18007a92c  mov     [rsp+48h+lpString2], rax; lpString2
0x18007a931  lea     edx, [r9+2]; dwCmpFlags
0x18007a935  call    cs:__imp_CompareStringW
0x18007a93c  nop     dword ptr [rax+rax+00h]
0x18007a941  mov     rcx, [rsp+48h+arg_0]
0x18007a946  lea     r8, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x18007a94d  xor     ebp, ebp
0x18007a94f  mov     r9, rsi
0x18007a952  cmp     eax, 2
0x18007a955  mov     rax, [rdi+58h]
0x18007a959  mov     rcx, [rcx+10h]
0x18007a95d  cmovnz  rbp, rbx
0x18007a961  mov     rdx, rbp
0x18007a964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a969  lea     rdx, [rsp+48h+arg_10]; unsigned int *
0x18007a96e  mov     dword ptr [rsp+48h+arg_10], eax
0x18007a972  mov     ebx, eax
0x18007a974  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x18007a979  test    al, al
0x18007a97b  jz      short loc_18007A9CA
0x18007a97d  lea     rdx, [rsp+48h+arg_0]
0x18007a982  mov     rcx, rdi; void *
0x18007a985  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x18007a98a  mov     ebx, eax
0x18007a98c  test    eax, eax
0x18007a98e  js      short loc_18007A9D7
0x18007a990  mov     rcx, [rsp+48h+arg_0]
0x18007a995  lea     r8, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x18007a99c  mov     rax, [rdi+58h]
0x18007a9a0  mov     r9, rsi
0x18007a9a3  mov     rdx, rbp
0x18007a9a6  mov     rcx, [rcx+10h]
0x18007a9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007a9af  lea     rdx, [rsp+48h+arg_10]; unsigned int *
0x18007a9b4  mov     dword ptr [rsp+48h+arg_10], eax
0x18007a9b8  mov     ebx, eax
0x18007a9ba  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x18007a9bf  test    al, al
0x18007a9c1  jz      short loc_18007A9CA
0x18007a9c3  mov     ebx, 6Eh ; 'n'
0x18007a9c8  jmp     short loc_18007A9CE
0x18007a9ca  test    ebx, ebx
0x18007a9cc  jle     short loc_18007A9D7
0x18007a9ce  movzx   ebx, bx
0x18007a9d1  or      ebx, 80070000h
0x18007a9d7  lea     rcx, [rsp+48h+arg_0]
0x18007a9dc  call    ??1?$RefCounted@VCHealthConnection@Health@Wsp@@@Health@Wsp@@QEAA@XZ; Wsp::Health::RefCounted<Wsp::Health::CHealthConnection>::~RefCounted<Wsp::Health::CHealthConnection>(void)
0x18007a9e1  mov     eax, ebx
0x18007a9e3  mov     rbx, [rsp+48h+arg_8]
0x18007a9e8  add     rsp, 30h
0x18007a9ec  pop     rdi
0x18007a9ed  pop     rsi
0x18007a9ee  pop     rbp
0x18007a9ef  retn
```
