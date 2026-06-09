# Wsp::Health::ResClient::GetActions(wchar_t const *,wchar_t const *,void (*)(_HEALTH_ACTION_CLIENT *,void *),void *)

- ea: `0x18006f918`
- end: `0x18006fa8d`
- name: `?GetActions@ResClient@Health@Wsp@@QEAAJPEB_W0P6AXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z2@Z`
- size: `373`
- prototype: `__int64 __usercall@<rax>(Wsp::Health::ResClient *__hidden this@<rcx>, PCNZWCH lpString1@<rdx>, const wchar_t *@<r8>, void (*)(struct _HEALTH_ACTION_CLIENT *, void *)@<r9>, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18006e9a8`

## callees

- `0x18006f170`
- `0x18006f918`
- `0x18006fa94`
- `0x180070aec`
- `0x1800a9010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f993`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f9c2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f993`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006f9c2`

## pseudocode

```c
__int64 __fastcall Wsp::Health::ResClient::GetActions(
        Wsp::Health::ResClient *this,
        PCNZWCH lpString1,
        const wchar_t *a3,
        void (*a4)(struct _HEALTH_ACTION_CLIENT *, void *),
        void *a5)
{
  signed int Connection; // ebx
  PCNZWCH v9; // rsi
  int v10; // eax
  void *v11; // r14
  const WCHAR *v12; // rbp
  Wsp::Health::ResClient *v13; // rcx
  Wsp::Health::ResClient *v14; // rcx
  const wchar_t *v15; // [rsp+70h] [rbp+18h] BYREF
  void (*v16)(struct _HEALTH_ACTION_CLIENT *, void *); // [rsp+78h] [rbp+20h] BYREF

  v16 = a4;
  v15 = a3;
  if ( !*((_QWORD *)this + 10) )
    return 2147943557LL;
  v15 = 0;
  if ( (int)Wsp::Health::ResClient::GetConnection(this) >= 0 )
  {
    v9 = 0;
    if ( CompareStringW(0x400u, 1u, lpString1, -1, &base, -1) != 2 )
      v9 = lpString1;
    v10 = CompareStringW(0x400u, 1u, L"Microsoft.Health.EntityType.Fileshare", -1, &base, -1);
    v11 = a5;
    v12 = 0;
    if ( v10 != 2 )
      v12 = L"Microsoft.Health.EntityType.Fileshare";
    LODWORD(v16) = (*((__int64 (__fastcall **)(_QWORD, PCNZWCH, const WCHAR *, void (__fastcall *)(Wsp::Health *__hidden, struct _HEALTH_ACTION_CLIENT *, void *), void *))this
                    + 10))(
                     *((_QWORD *)v15 + 2),
                     v9,
                     v12,
                     Wsp::Health::HealthGetActionsApiCallback,
                     a5);
    Connection = (int)v16;
    if ( !Wsp::Health::ResClient::ValidateOperation(v13, (unsigned int *)&v16) )
      goto LABEL_13;
    Connection = Wsp::Health::ResClient::GetConnection(this);
    if ( Connection < 0 )
      goto LABEL_15;
    LODWORD(v16) = (*((__int64 (__fastcall **)(_QWORD, PCNZWCH, const WCHAR *, void (__fastcall *)(Wsp::Health *__hidden, struct _HEALTH_ACTION_CLIENT *, void *), void *))this
                    + 10))(
                     *((_QWORD *)v15 + 2),
                     v9,
                     v12,
                     Wsp::Health::HealthGetActionsApiCallback,
                     v11);
    Connection = (int)v16;
    if ( Wsp::Health::ResClient::ValidateOperation(v14, (unsigned int *)&v16) )
    {
      LOWORD(Connection) = 110;
    }
    else
    {
LABEL_13:
      if ( Connection <= 0 )
        goto LABEL_15;
    }
    Connection = (unsigned __int16)Connection | 0x80070000;
    goto LABEL_15;
  }
  Connection = -2147024786;
LABEL_15:
  Wsp::Health::RefCounted<Wsp::Health::CHealthConnection>::~RefCounted<Wsp::Health::CHealthConnection>(&v15);
  return (unsigned int)Connection;
}

```

## disassembly

```asm
0x18006f918  mov     [rsp+arg_0], rbx
0x18006f91d  mov     [rsp+arg_18], r9
0x18006f922  mov     [rsp+arg_10], r8
0x18006f927  push    rbp
0x18006f928  push    rsi
0x18006f929  push    rdi
0x18006f92a  push    r14
0x18006f92c  push    r15
0x18006f92e  sub     rsp, 30h
0x18006f932  cmp     qword ptr [rcx+50h], 0
0x18006f937  mov     rbx, rdx
0x18006f93a  mov     rdi, rcx
0x18006f93d  jnz     short loc_18006F949
0x18006f93f  mov     eax, 80070485h
0x18006f944  jmp     loc_18006FA7C
0x18006f949  lea     rdx, [rsp+58h+arg_10]
0x18006f94e  mov     [rsp+58h+arg_10], 0
0x18006f957  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x18006f95c  test    eax, eax
0x18006f95e  jns     short loc_18006F96A
0x18006f960  mov     ebx, 8007006Eh
0x18006f965  jmp     loc_18006FA70
0x18006f96a  or      r9d, 0FFFFFFFFh; cchCount1
0x18006f96e  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18006f976  mov     ebp, 400h
0x18006f97b  lea     r15, base
0x18006f982  mov     r8, rbx; lpString1
0x18006f985  mov     [rsp+58h+lpString2], r15; lpString2
0x18006f98a  mov     ecx, ebp; Locale
0x18006f98c  lea     r14d, [r9+2]
0x18006f990  mov     edx, r14d; dwCmpFlags
0x18006f993  call    cs:__imp_CompareStringW
0x18006f999  xor     esi, esi
0x18006f99b  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x18006f9a3  cmp     eax, 2
0x18006f9a6  mov     [rsp+58h+lpString2], r15; lpString2
0x18006f9ab  mov     edx, r14d; dwCmpFlags
0x18006f9ae  mov     ecx, ebp; Locale
0x18006f9b0  cmovnz  rsi, rbx
0x18006f9b4  lea     rbx, String1; "Microsoft.Health.EntityType.Fileshare"
0x18006f9bb  mov     r8, rbx; lpString1
0x18006f9be  or      r9d, 0FFFFFFFFh; cchCount1
0x18006f9c2  call    cs:__imp_CompareStringW
0x18006f9c8  mov     rcx, [rsp+58h+arg_10]
0x18006f9cd  lea     r9, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x18006f9d4  mov     r14, [rsp+58h+arg_20]
0x18006f9dc  xor     ebp, ebp
0x18006f9de  cmp     eax, 2
0x18006f9e1  mov     [rsp+58h+lpString2], r14
0x18006f9e6  mov     rax, [rdi+50h]
0x18006f9ea  mov     rdx, rsi
0x18006f9ed  mov     rcx, [rcx+10h]
0x18006f9f1  cmovnz  rbp, rbx
0x18006f9f5  mov     r8, rbp
0x18006f9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f9fd  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x18006fa02  mov     dword ptr [rsp+58h+arg_18], eax
0x18006fa06  mov     ebx, eax
0x18006fa08  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x18006fa0d  test    al, al
0x18006fa0f  jz      short loc_18006FA63
0x18006fa11  lea     rdx, [rsp+58h+arg_10]
0x18006fa16  mov     rcx, rdi; void *
0x18006fa19  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x18006fa1e  mov     ebx, eax
0x18006fa20  test    eax, eax
0x18006fa22  js      short loc_18006FA70
0x18006fa24  mov     rcx, [rsp+58h+arg_10]
0x18006fa29  lea     r9, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x18006fa30  mov     rax, [rdi+50h]
0x18006fa34  mov     r8, rbp
0x18006fa37  mov     rdx, rsi
0x18006fa3a  mov     [rsp+58h+lpString2], r14
0x18006fa3f  mov     rcx, [rcx+10h]
0x18006fa43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006fa48  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x18006fa4d  mov     dword ptr [rsp+58h+arg_18], eax
0x18006fa51  mov     ebx, eax
0x18006fa53  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x18006fa58  test    al, al
0x18006fa5a  jz      short loc_18006FA63
0x18006fa5c  mov     ebx, 6Eh ; 'n'
0x18006fa61  jmp     short loc_18006FA67
0x18006fa63  test    ebx, ebx
0x18006fa65  jle     short loc_18006FA70
0x18006fa67  movzx   ebx, bx
0x18006fa6a  or      ebx, 80070000h
0x18006fa70  lea     rcx, [rsp+58h+arg_10]
0x18006fa75  call    ??1?$RefCounted@VCHealthConnection@Health@Wsp@@@Health@Wsp@@QEAA@XZ; Wsp::Health::RefCounted<Wsp::Health::CHealthConnection>::~RefCounted<Wsp::Health::CHealthConnection>(void)
0x18006fa7a  mov     eax, ebx
0x18006fa7c  mov     rbx, [rsp+58h+arg_0]
0x18006fa81  add     rsp, 30h
0x18006fa85  pop     r15
0x18006fa87  pop     r14
0x18006fa89  pop     rdi
0x18006fa8a  pop     rsi
0x18006fa8b  pop     rbp
0x18006fa8c  retn
```
