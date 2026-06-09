# CPort::Initialize(CTrkWksSvc *,ulong)

- ea: `0x18000a65c`
- end: `0x18000a87a`
- name: `?Initialize@CPort@@QEAAXPEAVCTrkWksSvc@@K@Z`
- size: `542`
- prototype: `void __fastcall(CPort *__hidden this, struct CTrkWksSvc *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a524`

## callees

- `0x18000a4b8`
- `0x18000a65c`
- `0x18000ad70`
- `0x18000ada0`
- `0x18000af38`
- `0x18000af5c`
- `0x18000d020`
- `0x18000d1a0`
- `0x18000d228`
- `0x18000d39c`
- `0x18000d440`
- `0x18000feb0`
- `0x180010fca`
- `0x180011000`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x18000a7ca`
- `ntdll!NtOpenEvent` at `0x18000a7ca`
- `ntdll!NtAlpcCreatePort` at `0x18000a77c`
- `ntdll!NtAlpcCreatePort` at `0x18000a77c`
- `ntdll!RtlInitUnicodeString` at `0x18000a6f6`
- `ntdll!RtlInitUnicodeString` at `0x18000a7b6`
- `ntdll!RtlInitUnicodeString` at `0x18000a6f6`
- `ntdll!RtlInitUnicodeString` at `0x18000a7b6`

## string_xrefs

- `0x18000a6ea`: `\Security\TRKWKS_PORT`
- `0x18000a788`: `\Security\TRKWKS_PORT`
- `0x18000a7aa`: `\Security\TRKWKS_EVENT`
- `0x18000a7d6`: `\Security\TRKWKS_EVENT`

## pseudocode

```c
void __fastcall CPort::Initialize(CPort *this, struct CTrkWksSvc *a2, unsigned int a3)
{
  __int64 v3; // rsi
  int v6; // eax
  int v7; // ebx
  NTSTATUS v8; // eax
  int v9; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-108h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE v12[48]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v13[16]; // [rsp+90h] [rbp-98h] BYREF
  _BYTE v14[16]; // [rsp+A0h] [rbp-88h] BYREF
  _DWORD v15[4]; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v16; // [rsp+C0h] [rbp-68h]

  v3 = a3;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(v15, 0, 0x48u);
  DestinationString = 0;
  CSystemSD::CSystemSD((CSystemSD *)v12);
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 7) = a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 2) &= ~2u;
  RtlInitUnicodeString(&DestinationString, L"\\Security\\TRKWKS_PORT");
  CSystemSD::Initialize(v12);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityDescriptor = (PVOID)CSecDescriptor::operator void * const((__int64)v12);
  ObjectAttributes.SecurityQualityOfService = 0;
  memset_0(v15, 0, 0x48u);
  v15[0] = 393216;
  v16 = 184;
  v6 = NtAlpcCreatePort((char *)this + 24, &ObjectAttributes, v15);
  v7 = v6;
  if ( v6 < 0 )
  {
    TrkReportInternalError(0x6Du, 0x83u, v6, L"\\Security\\TRKWKS_PORT");
    TrkRaiseException(v7);
  }
  *((_DWORD *)this + 2) |= 1u;
  RtlInitUnicodeString(&DestinationString, L"\\Security\\TRKWKS_EVENT");
  v8 = NtOpenEvent((PHANDLE)this + 5, 0x1F0003u, &ObjectAttributes);
  v9 = v8;
  if ( v8 < 0 )
  {
    TrkReportInternalError(0x6Du, 0x94u, v8, L"\\Security\\TRKWKS_EVENT");
    TrkRaiseException(v9);
  }
  if ( !(unsigned int)CPort::RegisterWorkItemWithThreadPool(this) )
  {
    TrkReportInternalError(0x6Du, 0xA1u, v9, 0);
    TrkRaiseLastError();
  }
  *((_QWORD *)this + 6) = -10000000 * v3;
  CSID::UnInitialize((CSID *)v13);
  CSID::UnInitialize((CSID *)v14);
  CSecDescriptor::UnInitialize((CSecDescriptor *)v12);
  CSystemSD::~CSystemSD((CSystemSD *)v12);
}

```

## disassembly

```asm
0x18000a65c  mov     r11, rsp
0x18000a65f  mov     [r11+10h], rbx
0x18000a663  mov     [r11+18h], rsi
0x18000a667  push    rdi
0x18000a668  push    r14
0x18000a66a  push    r15
0x18000a66c  sub     rsp, 110h
0x18000a673  mov     rax, cs:__security_cookie
0x18000a67a  xor     rax, rsp
0x18000a67d  mov     [rsp+128h+var_28], rax
0x18000a685  mov     esi, r8d
0x18000a688  mov     r15, rdx
0x18000a68b  mov     rdi, rcx
0x18000a68e  xorps   xmm0, xmm0
0x18000a691  movups  xmmword ptr [rsp+128h+ObjectAttributes.Length], xmm0
0x18000a696  movups  xmmword ptr [rsp+128h+ObjectAttributes.ObjectName], xmm0
0x18000a69b  movups  xmmword ptr [rsp+128h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000a6a0  xor     edx, edx; Val
0x18000a6a2  lea     r8d, [rdx+48h]; Size
0x18000a6a6  lea     rcx, [r11-78h]; void *
0x18000a6aa  call    memset_0
0x18000a6af  xorps   xmm0, xmm0
0x18000a6b2  movups  xmmword ptr [rsp+128h+DestinationString.Length], xmm0
0x18000a6b7  lea     rcx, [rsp+128h+var_C8]; this
0x18000a6bc  call    ??0CSystemSD@@QEAA@XZ; CSystemSD::CSystemSD(void)
0x18000a6c1  nop
0x18000a6c2  mov     qword ptr [rdi+18h], 0
0x18000a6ca  mov     qword ptr [rdi+28h], 0
0x18000a6d2  mov     [rdi+38h], r15
0x18000a6d6  mov     qword ptr [rdi+20h], 0
0x18000a6de  mov     qword ptr [rdi+10h], 0
0x18000a6e6  and     dword ptr [rdi+8], 0FFFFFFFDh
0x18000a6ea  lea     rdx, SourceString; "\\Security\\TRKWKS_PORT"
0x18000a6f1  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x18000a6f6  call    cs:__imp_RtlInitUnicodeString
0x18000a6fc  lea     rcx, [rsp+128h+var_C8]
0x18000a701  call    ?Initialize@CSystemSD@@QEAAXW4ESystemSD@1@@Z; CSystemSD::Initialize(CSystemSD::ESystemSD)
0x18000a706  mov     [rsp+128h+ObjectAttributes.Length], 30h ; '0'
0x18000a70e  mov     [rsp+128h+ObjectAttributes.RootDirectory], 0
0x18000a717  mov     [rsp+128h+ObjectAttributes.Attributes], 0
0x18000a71f  lea     rax, [rsp+128h+DestinationString]
0x18000a724  mov     [rsp+128h+ObjectAttributes.ObjectName], rax
0x18000a729  lea     rcx, [rsp+128h+var_C8]
0x18000a72e  call    ??BCSecDescriptor@@QEAAQEAXXZ; CSecDescriptor::operator void * const(void)
0x18000a733  mov     [rsp+128h+ObjectAttributes.SecurityDescriptor], rax
0x18000a738  mov     [rsp+128h+ObjectAttributes.SecurityQualityOfService], 0
0x18000a741  xor     edx, edx; Val
0x18000a743  lea     r8d, [rdx+48h]; Size
0x18000a747  lea     rcx, [rsp+128h+var_78]; void *
0x18000a74f  call    memset_0
0x18000a754  mov     [rsp+128h+var_78], 60000h
0x18000a75f  mov     [rsp+128h+var_68], 0B8h
0x18000a76b  lea     r8, [rsp+128h+var_78]
0x18000a773  lea     rdx, [rsp+128h+ObjectAttributes]
0x18000a778  lea     rcx, [rdi+18h]
0x18000a77c  call    cs:__imp_NtAlpcCreatePort
0x18000a782  mov     ebx, eax
0x18000a784  test    eax, eax
0x18000a786  jns     short loc_18000A7A6
0x18000a788  lea     r9, SourceString; "\\Security\\TRKWKS_PORT"
0x18000a78f  mov     r8d, eax; int
0x18000a792  mov     edx, 83h; unsigned int
0x18000a797  lea     ecx, [rdx-16h]; unsigned int
0x18000a79a  call    ?TrkReportInternalError@@YAJKKJPEBG@Z; TrkReportInternalError(ulong,ulong,long,ushort const *)
0x18000a79f  mov     ecx, ebx; int
0x18000a7a1  call    ?TrkRaiseException@@YAXJ@Z; TrkRaiseException(long)
0x18000a7a6  or      dword ptr [rdi+8], 1
0x18000a7aa  lea     rdx, aSecurityTrkwks_0; "\\Security\\TRKWKS_EVENT"
0x18000a7b1  lea     rcx, [rsp+128h+DestinationString]; DestinationString
0x18000a7b6  call    cs:__imp_RtlInitUnicodeString
0x18000a7bc  lea     r8, [rsp+128h+ObjectAttributes]; ObjectAttributes
0x18000a7c1  mov     edx, 1F0003h; DesiredAccess
0x18000a7c6  lea     rcx, [rdi+28h]; EventHandle
0x18000a7ca  call    cs:__imp_NtOpenEvent
0x18000a7d0  mov     ebx, eax
0x18000a7d2  test    eax, eax
0x18000a7d4  jns     short loc_18000A7F4
0x18000a7d6  lea     r9, aSecurityTrkwks_0; "\\Security\\TRKWKS_EVENT"
0x18000a7dd  mov     r8d, eax; int
0x18000a7e0  mov     edx, 94h; unsigned int
0x18000a7e5  lea     ecx, [rdx-27h]; unsigned int
0x18000a7e8  call    ?TrkReportInternalError@@YAJKKJPEBG@Z; TrkReportInternalError(ulong,ulong,long,ushort const *)
0x18000a7ed  mov     ecx, ebx; int
0x18000a7ef  call    ?TrkRaiseException@@YAXJ@Z; TrkRaiseException(long)
0x18000a7f4  mov     rcx, rdi; this
0x18000a7f7  call    ?RegisterWorkItemWithThreadPool@CPort@@AEAAHXZ; CPort::RegisterWorkItemWithThreadPool(void)
0x18000a7fc  test    eax, eax
0x18000a7fe  jnz     short loc_18000A818
0x18000a800  xor     r9d, r9d; unsigned __int16 *
0x18000a803  mov     r8d, ebx; int
0x18000a806  mov     edx, 0A1h; unsigned int
0x18000a80b  lea     ecx, [rax+6Dh]; unsigned int
0x18000a80e  call    ?TrkReportInternalError@@YAJKKJPEBG@Z; TrkReportInternalError(ulong,ulong,long,ushort const *)
0x18000a813  call    ?TrkRaiseLastError@@YAXXZ; TrkRaiseLastError(void)
0x18000a818  imul    rcx, rsi, 0FFFFFFFFFF676980h
0x18000a81f  mov     [rdi+30h], rcx
0x18000a823  lea     rcx, [rsp+128h+var_98]; this
0x18000a82b  call    ?UnInitialize@CSID@@QEAAXXZ; CSID::UnInitialize(void)
0x18000a830  lea     rcx, [rsp+128h+var_88]; this
0x18000a838  call    ?UnInitialize@CSID@@QEAAXXZ; CSID::UnInitialize(void)
0x18000a83d  lea     rcx, [rsp+128h+var_C8]; this
0x18000a842  call    ?UnInitialize@CSecDescriptor@@QEAAXXZ; CSecDescriptor::UnInitialize(void)
0x18000a847  lea     rcx, [rsp+128h+var_C8]; this
0x18000a84c  call    ??1CSystemSD@@QEAA@XZ; CSystemSD::~CSystemSD(void)
0x18000a851  mov     rcx, [rsp+128h+var_28]
0x18000a859  xor     rcx, rsp; StackCookie
0x18000a85c  call    __security_check_cookie
0x18000a861  lea     r11, [rsp+128h+var_18]
0x18000a869  mov     rbx, [r11+28h]
0x18000a86d  mov     rsi, [r11+30h]
0x18000a871  mov     rsp, r11
0x18000a874  pop     r15
0x18000a876  pop     r14
0x18000a878  pop     rdi
0x18000a879  retn
0x180011717  push    rbp
0x180011719  sub     rsp, 20h
0x18001171d  mov     rbp, rdx
0x180011720  lea     rcx, [rbp+60h]; this
0x180011724  call    ?UnInitialize@CSystemSD@@QEAAXXZ; CSystemSD::UnInitialize(void)
0x180011729  nop
0x18001172a  add     rsp, 20h
0x18001172e  pop     rbp
0x18001172f  retn
```
