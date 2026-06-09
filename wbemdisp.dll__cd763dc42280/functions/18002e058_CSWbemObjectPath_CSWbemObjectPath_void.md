# CSWbemObjectPath::~CSWbemObjectPath(void)

- ea: `0x18002e058`
- end: `0x18002e115`
- name: `??1CSWbemObjectPath@@QEAA@XZ`
- size: `189`
- prototype: `void __fastcall(CSWbemObjectPath *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18002e490`

## callees

- `0x18000c8b0`
- `0x18002e058`
- `0x180036010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18002e0d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e0ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e0d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002e0ef`

## pseudocode

```c
void __fastcall CSWbemObjectPath::~CSWbemObjectPath(CSWbemObjectPath *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  OLECHAR *v4; // rcx
  OLECHAR *v5; // rcx

  *(_QWORD *)this = &CSWbemObjectPath::`vftable'{for `ISWbemObjectPath'};
  *((_QWORD *)this + 1) = &CSWbemObjectPath::`vftable'{for `IObjectSafety'};
  *((_QWORD *)this + 2) = &CSWbemObjectPath::`vftable'{for `ISupportErrorInfo'};
  *((_QWORD *)this + 3) = &CSWbemObjectPath::`vftable'{for `IProvideClassInfo'};
  v2 = *((_QWORD *)this + 14);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 14) = 0;
  }
  v3 = *((_QWORD *)this + 18);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 18) = 0;
  }
  v4 = (OLECHAR *)*((_QWORD *)this + 15);
  if ( v4 )
  {
    SysFreeString(v4);
    *((_QWORD *)this + 15) = 0;
  }
  v5 = (OLECHAR *)*((_QWORD *)this + 16);
  if ( v5 )
  {
    SysFreeString(v5);
    *((_QWORD *)this + 16) = 0;
  }
  _InterlockedDecrement(&g_cObj);
  CDispatchHelp::~CDispatchHelp((CSWbemObjectPath *)((char *)this + 32));
}

```

## disassembly

```asm
0x18002e058  push    rbx
0x18002e05a  sub     rsp, 20h
0x18002e05e  mov     rbx, rcx
0x18002e061  lea     rax, ??_7CSWbemObjectPath@@6BISWbemObjectPath@@@; const CSWbemObjectPath::`vftable'{for `ISWbemObjectPath'}
0x18002e068  mov     [rcx], rax
0x18002e06b  lea     rax, ??_7CSWbemObjectPath@@6BIObjectSafety@@@; const CSWbemObjectPath::`vftable'{for `IObjectSafety'}
0x18002e072  mov     [rcx+8], rax
0x18002e076  lea     rax, ??_7CSWbemObjectPath@@6BISupportErrorInfo@@@; const CSWbemObjectPath::`vftable'{for `ISupportErrorInfo'}
0x18002e07d  mov     [rcx+10h], rax
0x18002e081  lea     rax, ??_7CSWbemObjectPath@@6BIProvideClassInfo@@@; const CSWbemObjectPath::`vftable'{for `IProvideClassInfo'}
0x18002e088  mov     [rcx+18h], rax
0x18002e08c  mov     rcx, [rcx+70h]
0x18002e090  test    rcx, rcx
0x18002e093  jz      short loc_18002E0A9
0x18002e095  mov     rax, [rcx]
0x18002e098  mov     rax, [rax+10h]
0x18002e09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0a1  mov     qword ptr [rbx+70h], 0
0x18002e0a9  mov     rcx, [rbx+90h]
0x18002e0b0  test    rcx, rcx
0x18002e0b3  jz      short loc_18002E0CC
0x18002e0b5  mov     rax, [rcx]
0x18002e0b8  mov     rax, [rax+10h]
0x18002e0bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0c1  mov     qword ptr [rbx+90h], 0
0x18002e0cc  mov     rcx, [rbx+78h]; bstrString
0x18002e0d0  test    rcx, rcx
0x18002e0d3  jz      short loc_18002E0E3
0x18002e0d5  call    cs:__imp_SysFreeString
0x18002e0db  mov     qword ptr [rbx+78h], 0
0x18002e0e3  mov     rcx, [rbx+80h]; bstrString
0x18002e0ea  test    rcx, rcx
0x18002e0ed  jz      short loc_18002E100
0x18002e0ef  call    cs:__imp_SysFreeString
0x18002e0f5  mov     qword ptr [rbx+80h], 0
0x18002e100  lock dec cs:?g_cObj@@3JA; long g_cObj
0x18002e107  lea     rcx, [rbx+20h]; this
0x18002e10b  add     rsp, 20h
0x18002e10f  pop     rbx
0x18002e110  jmp     ??1CDispatchHelp@@UEAA@XZ; CDispatchHelp::~CDispatchHelp(void)
```
