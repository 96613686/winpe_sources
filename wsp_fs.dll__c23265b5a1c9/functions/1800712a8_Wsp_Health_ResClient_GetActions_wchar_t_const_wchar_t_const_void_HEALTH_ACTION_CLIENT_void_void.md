# Wsp::Health::ResClient::GetActions(wchar_t const *,wchar_t const *,void (*)(_HEALTH_ACTION_CLIENT *,void *),void *)

- ea: `0x1800712a8`
- end: `0x18007142a`
- name: `?GetActions@ResClient@Health@Wsp@@QEAAJPEB_W0P6AXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z2@Z`
- size: `386`
- prototype: `__int64 __usercall@<rax>(Wsp::Health::ResClient *__hidden this@<rcx>, PCNZWCH lpString1@<rdx>, const wchar_t *@<r8>, void (*)(struct _HEALTH_ACTION_CLIENT *, void *)@<r9>, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180070240`

## callees

- `0x180070a4c`
- `0x1800712a8`
- `0x180071430`
- `0x1800725f4`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071323`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071358`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071323`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180071358`

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
0x1800712a8  mov     [rsp+arg_0], rbx
0x1800712ad  mov     [rsp+arg_18], r9
0x1800712b2  mov     [rsp+arg_10], r8
0x1800712b7  push    rbp
0x1800712b8  push    rsi
0x1800712b9  push    rdi
0x1800712ba  push    r14
0x1800712bc  push    r15
0x1800712be  sub     rsp, 30h
0x1800712c2  cmp     qword ptr [rcx+50h], 0
0x1800712c7  mov     rbx, rdx
0x1800712ca  mov     rdi, rcx
0x1800712cd  jnz     short loc_1800712D9
0x1800712cf  mov     eax, 80070485h
0x1800712d4  jmp     loc_180071418
0x1800712d9  lea     rdx, [rsp+58h+arg_10]
0x1800712de  mov     [rsp+58h+arg_10], 0
0x1800712e7  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x1800712ec  test    eax, eax
0x1800712ee  jns     short loc_1800712FA
0x1800712f0  mov     ebx, 8007006Eh
0x1800712f5  jmp     loc_18007140C
0x1800712fa  or      r9d, 0FFFFFFFFh; cchCount1
0x1800712fe  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180071306  mov     ebp, 400h
0x18007130b  lea     r15, base
0x180071312  mov     r8, rbx; lpString1
0x180071315  mov     [rsp+58h+lpString2], r15; lpString2
0x18007131a  mov     ecx, ebp; Locale
0x18007131c  lea     r14d, [r9+2]
0x180071320  mov     edx, r14d; dwCmpFlags
0x180071323  call    cs:__imp_CompareStringW
0x18007132a  nop     dword ptr [rax+rax+00h]
0x18007132f  xor     esi, esi
0x180071331  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x180071339  cmp     eax, 2
0x18007133c  mov     [rsp+58h+lpString2], r15; lpString2
0x180071341  mov     edx, r14d; dwCmpFlags
0x180071344  mov     ecx, ebp; Locale
0x180071346  cmovnz  rsi, rbx
0x18007134a  lea     rbx, String1; "Microsoft.Health.EntityType.Fileshare"
0x180071351  mov     r8, rbx; lpString1
0x180071354  or      r9d, 0FFFFFFFFh; cchCount1
0x180071358  call    cs:__imp_CompareStringW
0x18007135f  nop     dword ptr [rax+rax+00h]
0x180071364  mov     rcx, [rsp+58h+arg_10]
0x180071369  lea     r9, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x180071370  mov     r14, [rsp+58h+arg_20]
0x180071378  xor     ebp, ebp
0x18007137a  cmp     eax, 2
0x18007137d  mov     [rsp+58h+lpString2], r14
0x180071382  mov     rax, [rdi+50h]
0x180071386  mov     rdx, rsi
0x180071389  mov     rcx, [rcx+10h]
0x18007138d  cmovnz  rbp, rbx
0x180071391  mov     r8, rbp
0x180071394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071399  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x18007139e  mov     dword ptr [rsp+58h+arg_18], eax
0x1800713a2  mov     ebx, eax
0x1800713a4  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x1800713a9  test    al, al
0x1800713ab  jz      short loc_1800713FF
0x1800713ad  lea     rdx, [rsp+58h+arg_10]
0x1800713b2  mov     rcx, rdi; void *
0x1800713b5  call    ?GetConnection@ResClient@Health@Wsp@@QEAAJAEAV?$RefCounted@VCHealthConnection@Health@Wsp@@@23@@Z; Wsp::Health::ResClient::GetConnection(Wsp::Health::RefCounted<Wsp::Health::CHealthConnection> &)
0x1800713ba  mov     ebx, eax
0x1800713bc  test    eax, eax
0x1800713be  js      short loc_18007140C
0x1800713c0  mov     rcx, [rsp+58h+arg_10]
0x1800713c5  lea     r9, ?HealthGetActionsApiCallback@Health@Wsp@@YAXPEAU_HEALTH_ACTION_CLIENT@@PEAX@Z; Wsp::Health::HealthGetActionsApiCallback(_HEALTH_ACTION_CLIENT *,void *)
0x1800713cc  mov     rax, [rdi+50h]
0x1800713d0  mov     r8, rbp
0x1800713d3  mov     rdx, rsi
0x1800713d6  mov     [rsp+58h+lpString2], r14
0x1800713db  mov     rcx, [rcx+10h]
0x1800713df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800713e4  lea     rdx, [rsp+58h+arg_18]; unsigned int *
0x1800713e9  mov     dword ptr [rsp+58h+arg_18], eax
0x1800713ed  mov     ebx, eax
0x1800713ef  call    ?ValidateOperation@ResClient@Health@Wsp@@AEAA_NAEAK@Z; Wsp::Health::ResClient::ValidateOperation(ulong &)
0x1800713f4  test    al, al
0x1800713f6  jz      short loc_1800713FF
0x1800713f8  mov     ebx, 6Eh ; 'n'
0x1800713fd  jmp     short loc_180071403
0x1800713ff  test    ebx, ebx
0x180071401  jle     short loc_18007140C
0x180071403  movzx   ebx, bx
0x180071406  or      ebx, 80070000h
0x18007140c  lea     rcx, [rsp+58h+arg_10]
0x180071411  call    ??1?$RefCounted@VCHealthConnection@Health@Wsp@@@Health@Wsp@@QEAA@XZ; Wsp::Health::RefCounted<Wsp::Health::CHealthConnection>::~RefCounted<Wsp::Health::CHealthConnection>(void)
0x180071416  mov     eax, ebx
0x180071418  mov     rbx, [rsp+58h+arg_0]
0x18007141d  add     rsp, 30h
0x180071421  pop     r15
0x180071423  pop     r14
0x180071425  pop     rdi
0x180071426  pop     rsi
0x180071427  pop     rbp
0x180071428  retn
```
