# CEventLog2::LogV(_EVENT_DESCRIPTOR const *,ulong,char *)

- ea: `0x18000145c`
- end: `0x18000155e`
- name: `?LogV@CEventLog2@@QEAAKPEBU_EVENT_DESCRIPTOR@@KPEAD@Z`
- size: `258`
- prototype: `__int64 __fastcall(REGHANDLE *this, const struct _EVENT_DESCRIPTOR *, unsigned int, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800010f0`

## callees

- `0x18000145c`
- `0x180001560`
- `0x180002080`
- `0x1800020f4`

## import_xrefs

- `ADVAPI32!EventWrite` at `0x180001514`
- `ADVAPI32!EventWrite` at `0x180001514`

## string_xrefs

- `0x180001520`: `onecore\base\eco\wds\wdslib\common\src\eventlog2.cpp`

## pseudocode

```c
__int64 __fastcall CEventLog2::LogV(REGHANDLE *this, const struct _EVENT_DESCRIPTOR *a2, unsigned int a3, char *a4)
{
  struct _EVENT_DATA_DESCRIPTOR *v4; // rdi
  __int64 v5; // rsi
  ULONG v6; // ebp
  __int64 v7; // r14
  ULONG v11; // ebx
  unsigned __int64 v12; // rax
  char *v13; // rax
  __int64 v14; // rdx
  union _EVENT_DATA_DESCRIPTOR::$535316677C6A15A6ECBA40D88E1D787B *p_Reserved; // rcx
  _DWORD *v16; // rax
  const char *v17; // rdx

  v4 = 0;
  v5 = a3;
  v6 = 0;
  v7 = 0;
  if ( *((_DWORD *)this + 2) )
  {
    if ( !a3 )
      goto LABEL_8;
    v12 = 16LL * a3;
    if ( !is_mul_ok(a3, 0x10u) )
      v12 = -1;
    v4 = (struct _EVENT_DATA_DESCRIPTOR *)operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
    if ( v4 )
    {
LABEL_8:
      if ( (_DWORD)v5 )
      {
        v13 = a4 - 8;
        v14 = v5;
        p_Reserved = (union _EVENT_DATA_DESCRIPTOR::$535316677C6A15A6ECBA40D88E1D787B *)&v4->Reserved;
        do
        {
          v13 += 8;
          if ( *(_DWORD *)v13 <= 5u )
          {
            v16 = v13 + 8;
            v6 = *v16;
            v13 = (char *)(v16 + 2);
            v7 = *(_QWORD *)v13;
          }
          p_Reserved->Reserved = 0;
          *(_QWORD *)&p_Reserved[-3].Reserved = v7;
          p_Reserved[-1].Reserved = v6;
          p_Reserved += 4;
          --v14;
        }
        while ( v14 );
      }
      v11 = EventWrite(*this, a2, v5, v4);
      ElValidateWin32(v11, v17, "onecore\\base\\eco\\wds\\wdslib\\common\\src\\eventlog2.cpp", 0x114u);
      if ( v4 )
        operator delete(v4);
    }
    else
    {
      return 8;
    }
  }
  else
  {
    return 50;
  }
  return v11;
}

```

## disassembly

```asm
0x18000145c  mov     rax, rsp
0x18000145f  mov     [rax+8], rbx
0x180001463  mov     [rax+10h], rbp
0x180001467  mov     [rax+18h], rsi
0x18000146b  mov     [rax+20h], rdi
0x18000146f  push    r12
0x180001471  push    r14
0x180001473  push    r15
0x180001475  sub     rsp, 20h
0x180001479  xor     edi, edi
0x18000147b  mov     esi, r8d
0x18000147e  xor     ebp, ebp
0x180001480  xor     r14d, r14d
0x180001483  mov     rbx, r9
0x180001486  mov     r12, rdx
0x180001489  mov     r15, rcx
0x18000148c  cmp     [rcx+8], edi
0x18000148f  jnz     short loc_180001499
0x180001491  lea     ebx, [rdi+32h]
0x180001494  jmp     loc_18000153D
0x180001499  test    r8d, r8d
0x18000149c  jz      short loc_1800014CD
0x18000149e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800014a5  mov     eax, 10h
0x1800014aa  mul     rsi
0x1800014ad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800014b4  cmovo   rax, rcx
0x1800014b8  mov     rcx, rax; unsigned __int64
0x1800014bb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800014c0  mov     rdi, rax
0x1800014c3  test    rax, rax
0x1800014c6  jnz     short loc_1800014CD
0x1800014c8  lea     ebx, [rax+8]
0x1800014cb  jmp     short loc_18000153D
0x1800014cd  test    esi, esi
0x1800014cf  jz      short loc_180001508
0x1800014d1  lea     rax, [rbx-8]
0x1800014d5  mov     rdx, rsi
0x1800014d8  mov     ebx, 8
0x1800014dd  lea     rcx, [rdi+0Ch]
0x1800014e1  add     rax, rbx
0x1800014e4  cmp     dword ptr [rax], 5
0x1800014e7  ja      short loc_1800014F4
0x1800014e9  add     rax, rbx
0x1800014ec  mov     ebp, [rax]
0x1800014ee  add     rax, rbx
0x1800014f1  mov     r14, [rax]
0x1800014f4  and     dword ptr [rcx], 0
0x1800014f7  mov     [rcx-0Ch], r14
0x1800014fb  mov     [rcx-4], ebp
0x1800014fe  add     rcx, 10h
0x180001502  sub     rdx, 1
0x180001506  jnz     short loc_1800014E1
0x180001508  mov     rcx, [r15]; RegHandle
0x18000150b  mov     r9, rdi; UserData
0x18000150e  mov     r8d, esi; UserDataCount
0x180001511  mov     rdx, r12; EventDescriptor
0x180001514  call    cs:__imp_EventWrite
0x18000151a  mov     r9d, 114h; unsigned int
0x180001520  lea     r8, aOnecoreBaseEco; "onecore\\base\\eco\\wds\\wdslib\\common"...
0x180001527  mov     ecx, eax; unsigned int
0x180001529  mov     ebx, eax
0x18000152b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x180001530  test    rdi, rdi
0x180001533  jz      short loc_18000153D
0x180001535  mov     rcx, rdi; Block
0x180001538  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000153d  mov     rbp, [rsp+38h+arg_8]
0x180001542  mov     eax, ebx
0x180001544  mov     rbx, [rsp+38h+arg_0]
0x180001549  mov     rsi, [rsp+38h+arg_10]
0x18000154e  mov     rdi, [rsp+38h+arg_18]
0x180001553  add     rsp, 20h
0x180001557  pop     r15
0x180001559  pop     r14
0x18000155b  pop     r12
0x18000155d  retn
```
