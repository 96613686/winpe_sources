# CUwfConfiguration::Initialize(void *)

- ea: `0x180008170`
- end: `0x1800082f7`
- name: `?Initialize@CUwfConfiguration@@QEAAJPEAX@Z`
- size: `391`
- prototype: `__int64 __fastcall(CUwfConfiguration *__hidden this, HANDLE)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800163b0`
- `0x180017230`

## callees

- `0x180006200`
- `0x180008170`
- `0x180008730`
- `0x18000de30`
- `0x18000df60`
- `0x18000e96c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000826a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000826a`

## string_xrefs

- `0x1800081c0`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Dynamic`
- `0x180008201`: `SYSTEM\CurrentControlSet\Services\UWFVOL\Parameters\Static`
- `0x180008255`: `UpdatedSettings`

## pseudocode

```c
__int64 __fastcall CUwfConfiguration::Initialize(CUwfConfiguration *this, HANDLE a2)
{
  enum WELL_KNOWN_SID_TYPE v4; // ecx
  bool v5; // r14
  HKEY *v6; // rcx
  REGSAM v7; // esi
  int v8; // eax
  signed int v9; // ebx
  void *v10; // rax
  HKEY *v11; // rcx
  int v12; // eax
  HKEY v13; // rcx
  LSTATUS v14; // eax
  DWORD Type; // [rsp+70h] [rbp+40h] BYREF
  unsigned int Data; // [rsp+78h] [rbp+48h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+50h] BYREF

  CUwfConfiguration::Close(this);
  LOBYTE(Type) = 0;
  v5 = CheckTokenMembershipHelper(v4, (bool *)&Type) >= 0 && (_BYTE)Type == 1;
  *((_QWORD *)this + 1) = a2;
  v6 = (HKEY *)((char *)this + 24);
  v7 = v5 ? 131103 : 131097;
  if ( a2 == (HANDLE)-1LL )
    v8 = CUwfRegKey::Open(
           v6,
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Dynamic",
           v7);
  else
    v8 = CUwfRegKey::OpenTransacted(
           v6,
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Dynamic",
           v7,
           a2);
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_19;
  v10 = (void *)*((_QWORD *)this + 1);
  v11 = (HKEY *)((char *)this + 32);
  v12 = v10 == (void *)-1LL
      ? CUwfRegKey::Open(
          v11,
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static",
          v7)
      : CUwfRegKey::OpenTransacted(
          v11,
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Services\\UWFVOL\\Parameters\\Static",
          v7,
          v10);
  v9 = v12;
  if ( v12 < 0 )
    goto LABEL_19;
  v13 = (HKEY)*((_QWORD *)this + 4);
  Data = 0;
  Type = 0;
  cbData = 4;
  v14 = RegQueryValueExW(v13, L"UpdatedSettings", 0, &Type, (LPBYTE)&Data, &cbData);
  v9 = v14;
  if ( !v14 )
  {
    if ( Type == 4 )
    {
      if ( cbData == 4 )
        goto LABEL_17;
      v9 = -2147024883;
    }
    else
    {
      v9 = -2147023267;
    }
LABEL_19:
    CUwfConfiguration::Close(this);
    *((_DWORD *)this + 4) = v9;
    return (unsigned int)v9;
  }
  if ( v14 > 0 )
    v9 = (unsigned __int16)v14 | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_19;
LABEL_17:
  v9 = CUwfStaticConfiguration::Open((CUwfConfiguration *)((char *)this + 40), v5, Data, 1, this);
  if ( v9 < 0 )
    goto LABEL_19;
  v9 = CUwfStaticConfiguration::Open((CUwfConfiguration *)((char *)this + 88), v5, Data, 0, this);
  if ( v9 < 0 )
    goto LABEL_19;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180008170  push    rbp
0x180008172  push    rbx
0x180008173  push    rsi
0x180008174  push    rdi
0x180008175  push    r12
0x180008177  push    r14
0x180008179  push    r15
0x18000817b  mov     rbp, rsp
0x18000817e  sub     rsp, 30h
0x180008182  mov     rbx, rdx
0x180008185  mov     rdi, rcx
0x180008188  call    ?Close@CUwfConfiguration@@QEAAXXZ; CUwfConfiguration::Close(void)
0x18000818d  lea     rdx, [rbp+Type]; bool *
0x180008191  mov     byte ptr [rbp+Type], 0
0x180008195  call    ?CheckTokenMembershipHelper@@YAJW4WELL_KNOWN_SID_TYPE@@PEA_N@Z; CheckTokenMembershipHelper(WELL_KNOWN_SID_TYPE,bool *)
0x18000819a  test    eax, eax
0x18000819c  js      short loc_1800081A9
0x18000819e  cmp     byte ptr [rbp+Type], 1
0x1800081a2  jnz     short loc_1800081A9
0x1800081a4  mov     r14b, 1
0x1800081a7  jmp     short loc_1800081AC
0x1800081a9  xor     r14b, r14b
0x1800081ac  mov     al, r14b
0x1800081af  mov     [rdi+8], rbx
0x1800081b3  neg     al
0x1800081b5  lea     rcx, [rdi+18h]; phkResult
0x1800081b9  mov     r12, 0FFFFFFFF80000002h
0x1800081c0  lea     r8, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x1800081c7  sbb     esi, esi
0x1800081c9  mov     rdx, r12; hKey
0x1800081cc  and     esi, 6
0x1800081cf  add     esi, 20019h
0x1800081d5  mov     r9d, esi; samDesired
0x1800081d8  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800081dc  jz      short loc_1800081EA
0x1800081de  mov     [rsp+30h+lpData], rbx; HANDLE
0x1800081e3  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x1800081e8  jmp     short loc_1800081EF
0x1800081ea  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800081ef  mov     ebx, eax
0x1800081f1  test    eax, eax
0x1800081f3  js      loc_1800082C1
0x1800081f9  mov     rax, [rdi+8]
0x1800081fd  lea     r15, [rdi+20h]
0x180008201  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\UW"...
0x180008208  mov     r9d, esi; samDesired
0x18000820b  mov     rdx, r12; hKey
0x18000820e  mov     rcx, r15; phkResult
0x180008211  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008215  jz      short loc_180008223
0x180008217  mov     [rsp+30h+lpData], rax; HANDLE
0x18000821c  call    ?OpenTransacted@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGKPEAX@Z; CUwfRegKey::OpenTransacted(HKEY__ *,ushort const *,ulong,void *)
0x180008221  jmp     short loc_180008228
0x180008223  call    ?Open@CUwfRegKey@@QEAAJPEAUHKEY__@@PEBGK@Z; CUwfRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008228  mov     ebx, eax
0x18000822a  test    eax, eax
0x18000822c  js      loc_1800082C1
0x180008232  mov     rcx, [r15]; hKey
0x180008235  lea     rax, [rbp+cbData]
0x180008239  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18000823e  lea     r9, [rbp+Type]; lpType
0x180008242  lea     rax, [rbp+Data]
0x180008246  mov     [rbp+Data], 0
0x18000824d  xor     r8d, r8d; lpReserved
0x180008250  mov     [rsp+30h+lpData], rax; lpData
0x180008255  lea     rdx, aUpdatedsetting; "UpdatedSettings"
0x18000825c  mov     [rbp+Type], 0
0x180008263  mov     [rbp+cbData], 4
0x18000826a  call    cs:__imp_RegQueryValueExW
0x180008270  mov     ebx, eax
0x180008272  test    eax, eax
0x180008274  jz      short loc_1800082DD
0x180008276  jle     short loc_180008281
0x180008278  movzx   ebx, ax
0x18000827b  or      ebx, 80070000h
0x180008281  test    ebx, ebx
0x180008283  js      short loc_1800082C1
0x180008285  mov     r8d, [rbp+Data]; unsigned int
0x180008289  lea     rcx, [rdi+28h]; this
0x18000828d  mov     r9b, 1; bool
0x180008290  mov     [rsp+30h+lpData], rdi; struct CUwfConfiguration *
0x180008295  mov     dl, r14b; bool
0x180008298  call    ?Open@CUwfStaticConfiguration@@QEAAJ_NK0PEAVCUwfConfiguration@@@Z; CUwfStaticConfiguration::Open(bool,ulong,bool,CUwfConfiguration *)
0x18000829d  mov     ebx, eax
0x18000829f  test    eax, eax
0x1800082a1  js      short loc_1800082C1
0x1800082a3  mov     r8d, [rbp+Data]; unsigned int
0x1800082a7  lea     rcx, [rdi+58h]; this
0x1800082ab  xor     r9d, r9d; bool
0x1800082ae  mov     [rsp+30h+lpData], rdi; struct CUwfConfiguration *
0x1800082b3  mov     dl, r14b; bool
0x1800082b6  call    ?Open@CUwfStaticConfiguration@@QEAAJ_NK0PEAVCUwfConfiguration@@@Z; CUwfStaticConfiguration::Open(bool,ulong,bool,CUwfConfiguration *)
0x1800082bb  mov     ebx, eax
0x1800082bd  test    eax, eax
0x1800082bf  jns     short loc_1800082CC
0x1800082c1  mov     rcx, rdi; this
0x1800082c4  call    ?Close@CUwfConfiguration@@QEAAXXZ; CUwfConfiguration::Close(void)
0x1800082c9  mov     [rdi+10h], ebx
0x1800082cc  mov     eax, ebx
0x1800082ce  add     rsp, 30h
0x1800082d2  pop     r15
0x1800082d4  pop     r14
0x1800082d6  pop     r12
0x1800082d8  pop     rdi
0x1800082d9  pop     rsi
0x1800082da  pop     rbx
0x1800082db  pop     rbp
0x1800082dc  retn
0x1800082dd  cmp     [rbp+Type], 4
0x1800082e1  jz      short loc_1800082EA
0x1800082e3  mov     ebx, 8007065Dh
0x1800082e8  jmp     short loc_1800082C1
0x1800082ea  cmp     [rbp+cbData], 4
0x1800082ee  jz      short loc_180008285
0x1800082f0  mov     ebx, 8007000Dh
0x1800082f5  jmp     short loc_1800082C1
```
