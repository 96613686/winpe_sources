# SAL2::CCrossProcWaitFor::CWaitForRec::Initialize(SAL2::CCrossProcWaitFor::SLE_WAITFOR_OBJ *,SAL2::CW32Sid *)

- ea: `0x180086068`
- end: `0x180086174`
- name: `?Initialize@CWaitForRec@CCrossProcWaitFor@SAL2@@AEAAJPEAUSLE_WAITFOR_OBJ@23@PEAVCW32Sid@3@@Z`
- size: `268`
- prototype: `int(SAL2::CCrossProcWaitFor::CWaitForRec *__hidden this, struct SAL2::CCrossProcWaitFor::SLE_WAITFOR_OBJ *, struct SAL2::CW32Sid *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180086a90`

## callees

- `0x180001c00`
- `0x180080b28`
- `0x1800812f8`
- `0x180085b7c`
- `0x180086068`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800860f9`
- `KERNEL32!CreateEventW` at `0x1800860f9`
- `KERNEL32!GetLastError` at `0x180086108`
- `KERNEL32!GetLastError` at `0x180086108`
- `KERNEL32!OpenEventW` at `0x18008612d`
- `KERNEL32!OpenEventW` at `0x18008612d`

## pseudocode

```c
__int64 __fastcall SAL2::CCrossProcWaitFor::CWaitForRec::Initialize(
        SAL2::CCrossProcWaitFor::CWaitForRec *this,
        struct SAL2::CCrossProcWaitFor::SLE_WAITFOR_OBJ *a2,
        struct SAL2::CW32Sid *a3,
        unsigned int *a4)
{
  _OWORD *v4; // rsi
  enum _ACCESS_MODE v7; // r8d
  unsigned int v8; // ebx
  int v9; // ebx
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v12; // rax
  unsigned __int16 *v14; // [rsp+28h] [rbp-290h]
  unsigned int v15[4]; // [rsp+30h] [rbp-288h] BYREF
  _BYTE v16[48]; // [rsp+40h] [rbp-278h] BYREF
  LPSECURITY_ATTRIBUTES lpEventAttributes; // [rsp+70h] [rbp-248h]
  WCHAR Name[264]; // [rsp+80h] [rbp-238h] BYREF

  v4 = (_OWORD *)((char *)a2 + 28);
  v15[0] = 0;
  SAL2::CreateSALGlobalSuffixedStringFromGUID(
    (struct SAL2::CCrossProcWaitFor::SLE_WAITFOR_OBJ *)((char *)a2 + 28),
    &stru_1800CAD98,
    (unsigned __int16 *)a3,
    a4,
    (unsigned int)Name,
    v14);
  SAL2::CSALSecurityObject::CSALSecurityObject((SAL2::CSALSecurityObject *)v16, a3, v7, 0x100002u, v15);
  v8 = v15[0];
  if ( !v15[0] )
  {
    EventW = CreateEventW(lpEventAttributes, 1, 0, Name);
    *((_QWORD *)this + 3) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError != 5 )
      {
        if ( LastError <= 0 )
          goto LABEL_12;
        v9 = (unsigned __int16)LastError;
        goto LABEL_4;
      }
      v12 = OpenEventW(0x100002u, 0, Name);
      *((_QWORD *)this + 3) = v12;
      if ( !v12 )
      {
        v8 = -2147024891;
        goto LABEL_12;
      }
    }
    v8 = 0;
    *(_OWORD *)((char *)this + 8) = *v4;
    goto LABEL_12;
  }
  if ( (int)v15[0] > 0 )
  {
    v9 = LOWORD(v15[0]);
LABEL_4:
    v8 = v9 | 0x80070000;
  }
LABEL_12:
  SAL2::CSALSecurityObject::~CSALSecurityObject((SAL2::CSALSecurityObject *)v16);
  return v8;
}

```

## disassembly

```asm
0x180086068  push    rbx
0x18008606a  push    rsi
0x18008606b  push    rdi
0x18008606c  sub     rsp, 2A0h
0x180086073  mov     rax, cs:__security_cookie
0x18008607a  xor     rax, rsp
0x18008607d  mov     [rsp+2B8h+var_28], rax
0x180086085  lea     rsi, [rdx+1Ch]
0x180086089  mov     [rsp+2B8h+var_288], 0
0x180086091  mov     rdi, rcx
0x180086094  lea     rax, [rsp+2B8h+Name]
0x18008609c  mov     rcx, rsi; this
0x18008609f  mov     [rsp+2B8h+var_298], rax; unsigned int
0x1800860a4  lea     rdx, stru_1800CAD98; struct _GUID *
0x1800860ab  mov     rbx, r8
0x1800860ae  call    ?CreateSALGlobalSuffixedStringFromGUID@SAL2@@YAJAEBU_GUID@@PEAGPEAKK1@Z; SAL2::CreateSALGlobalSuffixedStringFromGUID(_GUID const &,ushort *,ulong *,ulong,ushort *)
0x1800860b3  lea     rax, [rsp+2B8h+var_288]
0x1800860b8  mov     r9d, 100002h; unsigned int
0x1800860be  mov     rdx, rbx; struct SAL2::CW32Sid *
0x1800860c1  mov     [rsp+2B8h+var_298], rax; unsigned int *
0x1800860c6  lea     rcx, [rsp+2B8h+var_278]; this
0x1800860cb  call    ??0CSALSecurityObject@SAL2@@QEAA@PEAVCW32Sid@1@W4_ACCESS_MODE@@KPEAK@Z; SAL2::CSALSecurityObject::CSALSecurityObject(SAL2::CW32Sid *,_ACCESS_MODE,ulong,ulong *)
0x1800860d0  mov     ebx, [rsp+2B8h+var_288]
0x1800860d4  test    ebx, ebx
0x1800860d6  jz      short loc_1800860E5
0x1800860d8  jle     short loc_18008614D
0x1800860da  movzx   ebx, bx
0x1800860dd  or      ebx, 80070000h
0x1800860e3  jmp     short loc_18008614D
0x1800860e5  mov     rcx, [rsp+2B8h+lpEventAttributes]; lpEventAttributes
0x1800860ea  lea     r9, [rsp+2B8h+Name]; lpName
0x1800860f2  xor     r8d, r8d; bInitialState
0x1800860f5  lea     edx, [r8+1]; bManualReset
0x1800860f9  call    cs:__imp_CreateEventW
0x1800860ff  mov     [rdi+18h], rax
0x180086103  test    rax, rax
0x180086106  jnz     short loc_180086143
0x180086108  call    cs:__imp_GetLastError
0x18008610e  mov     ebx, eax
0x180086110  cmp     eax, 5
0x180086113  jz      short loc_18008611E
0x180086115  test    eax, eax
0x180086117  jle     short loc_18008614D
0x180086119  movzx   ebx, ax
0x18008611c  jmp     short loc_1800860DD
0x18008611e  lea     r8, [rsp+2B8h+Name]; lpName
0x180086126  xor     edx, edx; bInheritHandle
0x180086128  mov     ecx, 100002h; dwDesiredAccess
0x18008612d  call    cs:__imp_OpenEventW
0x180086133  mov     [rdi+18h], rax
0x180086137  test    rax, rax
0x18008613a  jnz     short loc_180086143
0x18008613c  mov     ebx, 80070005h
0x180086141  jmp     short loc_18008614D
0x180086143  movups  xmm0, xmmword ptr [rsi]
0x180086146  xor     ebx, ebx
0x180086148  movdqu  xmmword ptr [rdi+8], xmm0
0x18008614d  lea     rcx, [rsp+2B8h+var_278]; this
0x180086152  call    ??1CSALSecurityObject@SAL2@@UEAA@XZ; SAL2::CSALSecurityObject::~CSALSecurityObject(void)
0x180086157  mov     eax, ebx
0x180086159  mov     rcx, [rsp+2B8h+var_28]
0x180086161  xor     rcx, rsp; StackCookie
0x180086164  call    __security_check_cookie
0x180086169  add     rsp, 2A0h
0x180086170  pop     rdi
0x180086171  pop     rsi
0x180086172  pop     rbx
0x180086173  retn
```
