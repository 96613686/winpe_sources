# SAL2::CSALId::CSALId(SAL2::CW32Sid *,long *)

- ea: `0x1800807d0`
- end: `0x1800808c3`
- name: `??0CSALId@SAL2@@QEAA@PEAVCW32Sid@1@PEAJ@Z`
- size: `243`
- prototype: `__int64 __fastcall(SAL2::CSALId *__hidden this, struct SAL2::CW32Sid *, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18008035c`
- `0x180094ec8`

## callees

- `0x180001c00`
- `0x1800807d0`
- `0x180080a48`
- `0x1800812f8`
- `0x180085b7c`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180080878`
- `KERNEL32!CreateEventW` at `0x180080878`
- `KERNEL32!GetLastError` at `0x180080887`
- `KERNEL32!GetLastError` at `0x180080887`
- `ole32!CoCreateGuid` at `0x180080838`
- `ole32!CoCreateGuid` at `0x180080838`

## pseudocode

```c
SAL2::CSALId *__fastcall SAL2::CSALId::CSALId(SAL2::CSALId *this, struct SAL2::CW32Sid *a2, int *a3)
{
  HRESULT Guid; // eax
  unsigned __int16 *v6; // r8
  unsigned int *v7; // r9
  HANDLE EventW; // rax
  signed int LastError; // eax
  enum _ACCESS_MODE v11; // [rsp+20h] [rbp-2A8h]
  unsigned __int16 *v12; // [rsp+28h] [rbp-2A0h]
  unsigned int v13[4]; // [rsp+40h] [rbp-288h] BYREF
  _BYTE v14[48]; // [rsp+50h] [rbp-278h] BYREF
  LPSECURITY_ATTRIBUTES lpEventAttributes; // [rsp+80h] [rbp-248h]
  WCHAR Name[264]; // [rsp+90h] [rbp-238h] BYREF

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &SAL2::CSALId::`vftable';
  v13[0] = 0;
  SAL2::CSALSecurityObject::CSALSecurityObject(
    (SAL2::CSALSecurityObject *)v14,
    a2,
    (enum _ACCESS_MODE)a3,
    0x1F0003u,
    v11,
    2u,
    v13);
  if ( *a3 >= 0 )
  {
    Guid = CoCreateGuid((GUID *)this + 1);
    *a3 = Guid;
    if ( Guid >= 0 )
    {
      SAL2::CreateSALGlobalSuffixedStringFromGUID(
        (SAL2::CSALId *)((char *)this + 16),
        &stru_1800CACB0,
        v6,
        v7,
        (unsigned int)Name,
        v12);
      EventW = CreateEventW(lpEventAttributes, 1, 0, Name);
      *((_QWORD *)this + 1) = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        *a3 = LastError;
      }
    }
  }
  SAL2::CSALSecurityObject::~CSALSecurityObject((SAL2::CSALSecurityObject *)v14);
  return this;
}

```

## disassembly

```asm
0x1800807d0  push    rbx
0x1800807d2  push    rsi
0x1800807d3  push    rdi
0x1800807d4  sub     rsp, 2B0h
0x1800807db  mov     rax, cs:__security_cookie
0x1800807e2  xor     rax, rsp
0x1800807e5  mov     [rsp+2C8h+var_28], rax
0x1800807ed  lea     rax, ??_7CSALId@SAL2@@6B@; const SAL2::CSALId::`vftable'
0x1800807f4  mov     qword ptr [rcx+8], 0
0x1800807fc  mov     [rcx], rax
0x1800807ff  mov     rbx, rcx
0x180080802  lea     rax, [rsp+2C8h+var_288]
0x180080807  mov     [rsp+2C8h+var_288], 0
0x18008080f  mov     [rsp+2C8h+var_298], rax; unsigned int *
0x180080814  lea     rcx, [rsp+2C8h+var_278]; this
0x180080819  mov     r9d, 1F0003h; unsigned int
0x18008081f  mov     dword ptr [rsp+2C8h+var_2A0], 2; unsigned __int16 *
0x180080827  mov     rdi, r8
0x18008082a  call    ??0CSALSecurityObject@SAL2@@QEAA@PEAVCW32Sid@1@W4_ACCESS_MODE@@K1KPEAK@Z; SAL2::CSALSecurityObject::CSALSecurityObject(SAL2::CW32Sid *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,ulong *)
0x18008082f  cmp     dword ptr [rdi], 0
0x180080832  jl      short loc_18008089B
0x180080834  lea     rcx, [rbx+10h]; pguid
0x180080838  call    cs:__imp_CoCreateGuid
0x18008083e  mov     [rdi], eax
0x180080840  test    eax, eax
0x180080842  js      short loc_18008089B
0x180080844  lea     rax, [rsp+2C8h+Name]
0x18008084c  lea     rdx, stru_1800CACB0; struct _GUID *
0x180080853  mov     qword ptr [rsp+2C8h+var_2A8], rax; unsigned int
0x180080858  lea     rcx, [rbx+10h]; this
0x18008085c  call    ?CreateSALGlobalSuffixedStringFromGUID@SAL2@@YAJAEBU_GUID@@PEAGPEAKK1@Z; SAL2::CreateSALGlobalSuffixedStringFromGUID(_GUID const &,ushort *,ulong *,ulong,ushort *)
0x180080861  mov     rcx, [rsp+2C8h+lpEventAttributes]; lpEventAttributes
0x180080869  lea     r9, [rsp+2C8h+Name]; lpName
0x180080871  xor     r8d, r8d; bInitialState
0x180080874  lea     edx, [r8+1]; bManualReset
0x180080878  call    cs:__imp_CreateEventW
0x18008087e  mov     [rbx+8], rax
0x180080882  test    rax, rax
0x180080885  jnz     short loc_18008089B
0x180080887  call    cs:__imp_GetLastError
0x18008088d  test    eax, eax
0x18008088f  jle     short loc_180080899
0x180080891  movzx   eax, ax
0x180080894  or      eax, 80070000h
0x180080899  mov     [rdi], eax
0x18008089b  lea     rcx, [rsp+2C8h+var_278]; this
0x1800808a0  call    ??1CSALSecurityObject@SAL2@@UEAA@XZ; SAL2::CSALSecurityObject::~CSALSecurityObject(void)
0x1800808a5  mov     rax, rbx
0x1800808a8  mov     rcx, [rsp+2C8h+var_28]
0x1800808b0  xor     rcx, rsp; StackCookie
0x1800808b3  call    __security_check_cookie
0x1800808b8  add     rsp, 2B0h
0x1800808bf  pop     rdi
0x1800808c0  pop     rsi
0x1800808c1  pop     rbx
0x1800808c2  retn
```
