# _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>(unsigned __int64,bool,uus::UusInfo,wchar_t const *,wchar_t const *,std::chrono::duration<__int64,std::ratio<1,1>> const &,wchar_t const *,wchar_t const *,std::chrono::duration<int,std::ratio<60,1>>)

- ea: `0x18000e888`
- end: `0x18000ea30`
- name: `??$?0_JU?$ratio@$00$00@std@@@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@QEAA@_K_NUUusInfo@uus@@PEB_W3AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@33V?$duration@HU?$ratio@$0DM@$00@std@@@45@@Z`
- size: `424`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18001aa50`
- `0x180039ee0`

## callees

- `0x180009300`
- `0x1800094bc`
- `0x180009938`
- `0x18000e888`
- `0x180014338`
- `0x180015af8`
- `0x180015c0c`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::_StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>(
        __int64 a1,
        __int64 a2,
        bool a3,
        struct uus::UusInfo *a4,
        __int64 a5,
        wchar_t *a6,
        _QWORD *a7,
        wchar_t *a8,
        wchar_t *a9,
        int a10)
{
  __int64 v13; // rdi
  __int64 v14; // rax
  struct uus::UusInfo *v15; // rdx
  struct uus::UusInfo *v16; // r10
  unsigned __int64 v17; // rax
  void **v19; // [rsp+50h] [rbp-71h] BYREF
  struct uus::UusInfo *v20; // [rsp+58h] [rbp-69h]
  void **v21; // [rsp+60h] [rbp-61h] BYREF
  __int64 v22; // [rsp+68h] [rbp-59h]
  struct uus::UusInfo *v23[3]; // [rsp+70h] [rbp-51h] BYREF
  wchar_t *v24; // [rsp+88h] [rbp-39h]
  wchar_t *v25; // [rsp+90h] [rbp-31h]
  __int64 v26; // [rsp+98h] [rbp-29h]
  void **v27; // [rsp+A0h] [rbp-21h]
  struct uus::UusInfo *v28; // [rsp+A8h] [rbp-19h]
  void **v29; // [rsp+B0h] [rbp-11h]
  unsigned __int64 v30; // [rsp+B8h] [rbp-9h]

  v23[0] = a4;
  v26 = a1;
  v25 = a8;
  v24 = a9;
  *(_QWORD *)a1 = &_StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::`vftable';
  v13 = a1 + 8;
  _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::InitFilePath(
    (struct std::error_code *)(a1 + 8),
    a5,
    (__int64)a6);
  *(_QWORD *)(a1 + 48) = -1;
  *(_QWORD *)(a1 + 40) = &StackLockFileWin32Reader::`vftable';
  *(_QWORD *)(a1 + 56) = a2;
  _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::TryUpdateVerGetPrevious(a1 + 64, v13, a2);
  v14 = _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::InitActiveVer<__int64,std::ratio<1,1>>(
          v13,
          a7,
          a1 + 40);
  v15 = (struct uus::UusInfo *)v14;
  *(_QWORD *)(a1 + 80) = v14;
  v16 = *(struct uus::UusInfo **)(a1 + 56);
  if ( *(_BYTE *)(a1 + 72) )
  {
    v17 = *(_QWORD *)(a1 + 64);
    if ( v16 == v15 )
    {
      v19 = &UusVersion::`vftable';
      v20 = (struct uus::UusInfo *)v17;
      v27 = &UusVersion::`vftable';
      v28 = v16;
      v29 = &UusVersion::`vftable';
      v30 = v17;
      v21 = &UusVersion::`vftable';
      v22 = (__int64)v16;
      uus::UndockedUpdateCoreTelemetry::UusUpdatedActiveVersion(
        (const struct UusVersion *)&v21,
        a3,
        v23[0],
        (unsigned __int64)v16 < v17,
        (const struct UusVersion *)&v19,
        a6,
        v25,
        v24,
        a10);
    }
    else
    {
      v21 = &UusVersion::`vftable';
      v22 = v17;
      v19 = &UusVersion::`vftable';
      v20 = v15;
      v23[0] = (struct uus::UusInfo *)&UusVersion::`vftable';
      v23[1] = v16;
      uus::UndockedUpdateTelemetry::UusUpdatedButChangedBeforeReread(
        (const struct UusVersion *)v23,
        a3,
        (const struct UusVersion *)&v19,
        (const struct UusVersion *)&v21,
        a6);
    }
  }
  else if ( v16 != (struct uus::UusInfo *)v14 )
  {
    v21 = &UusVersion::`vftable';
    v22 = v14;
    v19 = &UusVersion::`vftable';
    v20 = v16;
    uus::UndockedUpdateTelemetry::UusUnableToUpdateActiveVersion(
      (const struct UusVersion *)&v19,
      a3,
      (const struct UusVersion *)&v21,
      a6);
  }
  return a1;
}

```

## disassembly

```asm
0x18000e888  push    rbp
0x18000e88a  push    rbx
0x18000e88b  push    rsi
0x18000e88c  push    rdi
0x18000e88d  push    r12
0x18000e88f  push    r13
0x18000e891  push    r14
0x18000e893  push    r15
0x18000e895  lea     rbp, [rsp-7]
0x18000e89a  sub     rsp, 0C8h
0x18000e8a1  mov     [rbp+3Fh+var_90], r9
0x18000e8a5  mov     r15b, r8b
0x18000e8a8  mov     rsi, rdx
0x18000e8ab  mov     r12, rcx
0x18000e8ae  mov     [rbp+3Fh+var_68], rcx
0x18000e8b2  mov     rdx, [rbp+3Fh+arg_20]
0x18000e8b6  mov     r14, [rbp+3Fh+arg_28]
0x18000e8ba  mov     rax, [rbp+3Fh+arg_38]
0x18000e8c1  mov     [rbp+3Fh+var_70], rax
0x18000e8c5  mov     rax, [rbp+3Fh+arg_40]
0x18000e8cc  mov     [rbp+3Fh+var_78], rax
0x18000e8d0  lea     rax, ??_7?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@6B@; const _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::`vftable'
0x18000e8d7  mov     [rcx], rax
0x18000e8da  lea     rdi, [rcx+8]
0x18000e8de  mov     r8, r14
0x18000e8e1  mov     rcx, rdi; struct std::error_code *
0x18000e8e4  call    ?InitFilePath@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@CA?AVpath@filesystem@std@@PEB_W0@Z; _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::InitFilePath(wchar_t const *,wchar_t const *)
0x18000e8e9  nop
0x18000e8ea  mov     qword ptr [r12+30h], 0FFFFFFFFFFFFFFFFh
0x18000e8f3  lea     rax, ??_7StackLockFileWin32Reader@@6B@; const StackLockFileWin32Reader::`vftable'
0x18000e8fa  mov     [r12+28h], rax
0x18000e8ff  mov     [r12+38h], rsi
0x18000e904  lea     r13, [r12+40h]
0x18000e909  mov     r8, rsi
0x18000e90c  mov     rdx, rdi
0x18000e90f  mov     rcx, r13
0x18000e912  call    ?TryUpdateVerGetPrevious@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@CA?AV?$optional@_K@std@@AEBVpath@filesystem@3@_K@Z; _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::TryUpdateVerGetPrevious(std::filesystem::path const &,unsigned __int64)
0x18000e917  lea     r8, [r12+28h]
0x18000e91c  mov     rdx, [rbp+3Fh+arg_30]
0x18000e920  mov     rcx, rdi
0x18000e923  call    ??$InitActiveVer@_JU?$ratio@$00$00@std@@@?$_StackLockFile@UStackLockFileWin32Reader@@UStackLockFileWin32Writer@@@@CA_KAEBVpath@filesystem@std@@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@3@AEAUStackLockFileReader@@@Z; _StackLockFile<StackLockFileWin32Reader,StackLockFileWin32Writer>::InitActiveVer<__int64,std::ratio<1,1>>(std::filesystem::path const &,std::chrono::duration<__int64,std::ratio<1,1>> const &,StackLockFileReader &)
0x18000e928  mov     rdx, rax
0x18000e92b  mov     [r12+50h], rax
0x18000e930  mov     r10, [r12+38h]
0x18000e935  cmp     byte ptr [r12+48h], 0
0x18000e93b  jz      loc_18000E9E9
0x18000e941  lea     rcx, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18000e948  mov     rax, [r13+0]
0x18000e94c  cmp     r10, rdx
0x18000e94f  jnz     short loc_18000E9B5
0x18000e951  mov     [rbp+3Fh+var_B0], rcx
0x18000e955  mov     [rbp+3Fh+var_A8], rax
0x18000e959  mov     [rbp+3Fh+var_60], rcx
0x18000e95d  mov     [rbp+3Fh+var_58], r10
0x18000e961  mov     [rbp+3Fh+var_50], rcx
0x18000e965  mov     [rbp+3Fh+var_48], rax
0x18000e969  cmp     r10, rax
0x18000e96c  setb    r9b; bool
0x18000e970  mov     [rbp+3Fh+var_A0], rcx
0x18000e974  mov     [rbp+3Fh+var_98], r10
0x18000e978  mov     eax, [rbp+3Fh+arg_48]
0x18000e97e  mov     [rsp+100h+var_C0], eax; int
0x18000e982  mov     rax, [rbp+3Fh+var_78]
0x18000e986  mov     [rsp+100h+var_C8], rax; wchar_t *
0x18000e98b  mov     rax, [rbp+3Fh+var_70]
0x18000e98f  mov     [rsp+100h+var_D0], rax; wchar_t *
0x18000e994  mov     [rsp+100h+var_D8], r14; wchar_t *
0x18000e999  lea     rax, [rbp+3Fh+var_B0]
0x18000e99d  mov     [rsp+100h+var_E0], rax; struct UusVersion *
0x18000e9a2  mov     r8, [rbp+3Fh+var_90]; struct uus::UusInfo *
0x18000e9a6  mov     dl, r15b; bool
0x18000e9a9  lea     rcx, [rbp+3Fh+var_A0]; struct UusVersion *
0x18000e9ad  call    ?UusUpdatedActiveVersion@UndockedUpdateCoreTelemetry@uus@@SAXAEBVUusVersion@@_NAEBUUusInfo@2@10PEB_W33H@Z; uus::UndockedUpdateCoreTelemetry::UusUpdatedActiveVersion(UusVersion const &,bool,uus::UusInfo const &,bool,UusVersion const &,wchar_t const *,wchar_t const *,wchar_t const *,int)
0x18000e9b2  nop
0x18000e9b3  jmp     short loc_18000EA19
0x18000e9b5  mov     [rbp+3Fh+var_A0], rcx
0x18000e9b9  mov     [rbp+3Fh+var_98], rax
0x18000e9bd  mov     [rbp+3Fh+var_B0], rcx
0x18000e9c1  mov     [rbp+3Fh+var_A8], rdx
0x18000e9c5  mov     [rbp+3Fh+var_90], rcx
0x18000e9c9  mov     [rbp+3Fh+var_88], r10
0x18000e9cd  mov     [rsp+100h+var_E0], r14; wchar_t *
0x18000e9d2  lea     r9, [rbp+3Fh+var_A0]; struct UusVersion *
0x18000e9d6  lea     r8, [rbp+3Fh+var_B0]; struct UusVersion *
0x18000e9da  mov     dl, r15b; bool
0x18000e9dd  lea     rcx, [rbp+3Fh+var_90]; struct UusVersion *
0x18000e9e1  call    ?UusUpdatedButChangedBeforeReread@UndockedUpdateTelemetry@uus@@SAXAEBVUusVersion@@_N00PEB_W@Z; uus::UndockedUpdateTelemetry::UusUpdatedButChangedBeforeReread(UusVersion const &,bool,UusVersion const &,UusVersion const &,wchar_t const *)
0x18000e9e6  nop
0x18000e9e7  jmp     short loc_18000EA19
0x18000e9e9  cmp     r10, rdx
0x18000e9ec  jz      short loc_18000EA19
0x18000e9ee  lea     rcx, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18000e9f5  mov     [rbp+3Fh+var_A0], rcx
0x18000e9f9  mov     [rbp+3Fh+var_98], rdx
0x18000e9fd  mov     [rbp+3Fh+var_B0], rcx
0x18000ea01  mov     [rbp+3Fh+var_A8], r10
0x18000ea05  mov     r9, r14; wchar_t *
0x18000ea08  lea     r8, [rbp+3Fh+var_A0]; struct UusVersion *
0x18000ea0c  mov     dl, r15b; bool
0x18000ea0f  lea     rcx, [rbp+3Fh+var_B0]; struct UusVersion *
0x18000ea13  call    ?UusUnableToUpdateActiveVersion@UndockedUpdateTelemetry@uus@@SAXAEBVUusVersion@@_N0PEB_W@Z; uus::UndockedUpdateTelemetry::UusUnableToUpdateActiveVersion(UusVersion const &,bool,UusVersion const &,wchar_t const *)
0x18000ea18  nop
0x18000ea19  mov     rax, r12
0x18000ea1c  add     rsp, 0C8h
0x18000ea23  pop     r15
0x18000ea25  pop     r14
0x18000ea27  pop     r13
0x18000ea29  pop     r12
0x18000ea2b  pop     rdi
0x18000ea2c  pop     rsi
0x18000ea2d  pop     rbx
0x18000ea2e  pop     rbp
0x18000ea2f  retn
```
