# GetBackupConfigInfo(void *,SCAN_FUNCTION_ARGS,bool &)

- ea: `0x180018ea0`
- end: `0x180018fb6`
- name: `?GetBackupConfigInfo@@YAJPEAXUSCAN_FUNCTION_ARGS@@AEA_N@Z`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1800010b0`
- `0x18000198c`
- `0x180018ea0`
- `0x180018fbc`
- `0x1800191dc`
- `0x180019288`
- `0x1800194a8`

## pseudocode

```c
__int64 GetBackupConfigInfo()
{
  int IsFHConfigured; // ebx
  int IsWin7BackupConfigured; // eax
  int v2; // edi
  int IsKFMEnrolled; // eax
  int v4; // esi
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  bool v9; // [rsp+70h] [rbp+7h] BYREF
  bool v10[3]; // [rsp+71h] [rbp+8h] BYREF
  int v11; // [rsp+74h] [rbp+Bh] BYREF
  int v12; // [rsp+78h] [rbp+Fh] BYREF
  int v13; // [rsp+7Ch] [rbp+13h] BYREF
  int v14; // [rsp+80h] [rbp+17h] BYREF
  int v15; // [rsp+84h] [rbp+1Bh] BYREF
  int v16; // [rsp+88h] [rbp+1Fh] BYREF
  __int64 v17[6]; // [rsp+90h] [rbp+27h] BYREF
  bool v18; // [rsp+E8h] [rbp+7Fh] BYREF

  v10[0] = 0;
  v9 = 0;
  IsFHConfigured = GetIsFHConfigured(v10);
  IsWin7BackupConfigured = GetIsWin7BackupConfigured(&v9);
  v18 = 0;
  v2 = IsWin7BackupConfigured;
  IsKFMEnrolled = GetIsKFMEnrolled(&v18);
  v11 = 0;
  v4 = IsKFMEnrolled;
  GetBackupReminderToastCount((BYTE *)&v11);
  if ( (unsigned int)dword_180040010 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180040010, 0x400000000000LL) )
  {
    v16 = v11;
    v17[0] = 0x1000000;
    v12 = v6;
    v13 = v4;
    v14 = v2;
    v15 = IsFHConfigured;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v5,
      (unsigned int)&word_18003781E,
      v6,
      v7,
      (__int64)v10,
      (__int64)&v9,
      (__int64)&v18,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v14,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)v17);
  }
  return 0;
}

```

## disassembly

```asm
0x180018ea0  push    rbp
0x180018ea2  push    rbx
0x180018ea3  push    rsi
0x180018ea4  push    rdi
0x180018ea5  lea     rbp, [rsp-3Fh]
0x180018eaa  sub     rsp, 0A8h
0x180018eb1  lea     rcx, [rbp+57h+var_4F]; bool *
0x180018eb5  mov     [rbp+57h+var_4F], 0
0x180018eb9  call    ?GetIsFHConfigured@@YAJAEA_N@Z; GetIsFHConfigured(bool &)
0x180018ebe  lea     rcx, [rbp+57h+var_50]; bool *
0x180018ec2  mov     [rbp+57h+var_50], 0
0x180018ec6  mov     ebx, eax
0x180018ec8  call    ?GetIsWin7BackupConfigured@@YAJAEA_N@Z; GetIsWin7BackupConfigured(bool &)
0x180018ecd  lea     rcx, [rbp+57h+arg_18]; bool *
0x180018ed1  mov     [rbp+57h+arg_18], 0
0x180018ed5  mov     edi, eax
0x180018ed7  call    ?GetIsKFMEnrolled@@YAJAEA_N@Z; GetIsKFMEnrolled(bool &)
0x180018edc  lea     rcx, [rbp+57h+var_4C]; int *
0x180018ee0  mov     [rbp+57h+var_4C], 0
0x180018ee7  mov     esi, eax
0x180018ee9  call    ?GetBackupReminderToastCount@@YAJAEAH@Z; GetBackupReminderToastCount(int &)
0x180018eee  mov     ecx, cs:dword_180040010
0x180018ef4  mov     r8d, eax
0x180018ef7  cmp     ecx, 5
0x180018efa  jbe     loc_180018FA8
0x180018f00  mov     rdx, 400000000000h
0x180018f0a  lea     rcx, dword_180040010
0x180018f11  call    _tlgKeywordOn
0x180018f16  test    al, al
0x180018f18  jz      loc_180018FA8
0x180018f1e  mov     eax, [rbp+57h+var_4C]
0x180018f21  lea     rdx, word_18003781E
0x180018f28  mov     [rbp+57h+var_38], eax
0x180018f2b  mov     al, [rbp+57h+arg_18]
0x180018f2e  mov     [rbp+57h+arg_18], al
0x180018f31  mov     al, [rbp+57h+var_50]
0x180018f34  mov     [rbp+57h+var_50], al
0x180018f37  mov     al, [rbp+57h+var_4F]
0x180018f3a  mov     [rbp+57h+var_4F], al
0x180018f3d  lea     rax, [rbp+57h+var_30]
0x180018f41  mov     [rsp+0C0h+var_60], rax
0x180018f46  lea     rax, [rbp+57h+var_48]
0x180018f4a  mov     [rsp+0C0h+var_68], rax
0x180018f4f  lea     rax, [rbp+57h+var_44]
0x180018f53  mov     [rsp+0C0h+var_70], rax
0x180018f58  lea     rax, [rbp+57h+var_40]
0x180018f5c  mov     [rsp+0C0h+var_78], rax
0x180018f61  lea     rax, [rbp+57h+var_3C]
0x180018f65  mov     [rsp+0C0h+var_80], rax
0x180018f6a  lea     rax, [rbp+57h+var_38]
0x180018f6e  mov     [rsp+0C0h+var_88], rax
0x180018f73  lea     rax, [rbp+57h+arg_18]
0x180018f77  mov     [rsp+0C0h+var_90], rax
0x180018f7c  lea     rax, [rbp+57h+var_50]
0x180018f80  mov     [rsp+0C0h+var_98], rax
0x180018f85  lea     rax, [rbp+57h+var_4F]
0x180018f89  mov     [rsp+0C0h+var_A0], rax
0x180018f8e  mov     [rbp+57h+var_30], 1000000h
0x180018f96  mov     [rbp+57h+var_48], r8d
0x180018f9a  mov     [rbp+57h+var_44], esi
0x180018f9d  mov     [rbp+57h+var_40], edi
0x180018fa0  mov     [rbp+57h+var_3C], ebx
0x180018fa3  call    ??$Write@U?$_tlgWrapperByVal@$00@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@33AEBU?$_tlgWrapperByVal@$03@@4444AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180018fa8  xor     eax, eax
0x180018faa  add     rsp, 0A8h
0x180018fb1  pop     rdi
0x180018fb2  pop     rsi
0x180018fb3  pop     rbx
0x180018fb4  pop     rbp
0x180018fb5  retn
```
