# HMEHelpers::EnableServiceAccessForKey(ushort const *)

- ea: `0x18001699c`
- end: `0x180016a3d`
- name: `?EnableServiceAccessForKey@HMEHelpers@@YAJPEBG@Z`
- size: `161`
- prototype: `__int64 __fastcall(HMEHelpers *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180016e60`

## callees

- `0x18001699c`
- `0x180016b34`
- `0x18001cd1c`
- `0x18001ce68`
- `0x18001cf74`

## pseudocode

```c
__int64 __fastcall HMEHelpers::EnableServiceAccessForKey(HMEHelpers *this, const unsigned __int16 *a2, int a3)
{
  int v4; // ebx
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int16 *v12; // [rsp+30h] [rbp-18h] BYREF
  int v13; // [rsp+38h] [rbp-10h]
  __int16 v14; // [rsp+3Ch] [rbp-Ch]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  v4 = WString::Init((WString *)&v12, a2, a3);
  if ( v4 >= 0 )
  {
    v4 = WString::Concat((WString *)&v12, L"Software\\Microsoft\\MediaPlayer\\Preferences\\HME", v5);
    if ( v4 >= 0 )
    {
      v4 = WString::Concat((WString *)&v12, L"\\", v6);
      if ( v4 >= 0 )
      {
        v4 = WString::Concat((WString *)&v12, (const unsigned __int16 *)this, v7);
        if ( v4 >= 0 )
          v4 = HMEHelpers::ModifyObjectPermissions(v12, v8, v9, v10, GRANT_ACCESS);
      }
    }
  }
  WString::DeleteString(&v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001699c  mov     [rsp+arg_0], rbx
0x1800169a1  push    rdi
0x1800169a2  sub     rsp, 40h
0x1800169a6  mov     rdi, rcx
0x1800169a9  mov     [rsp+48h+var_18], 0
0x1800169b2  xor     eax, eax
0x1800169b4  mov     [rsp+48h+var_10], 0
0x1800169bc  lea     rcx, [rsp+48h+var_18]; this
0x1800169c1  mov     [rsp+48h+var_C], ax
0x1800169c6  call    ?Init@WString@@QEAAJPEBGH@Z; WString::Init(ushort const *,int)
0x1800169cb  mov     ebx, eax
0x1800169cd  test    eax, eax
0x1800169cf  js      short loc_180016A26
0x1800169d1  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\MediaPlayer\\Prefe"...
0x1800169d8  lea     rcx, [rsp+48h+var_18]; this
0x1800169dd  call    ?Concat@WString@@QEAAJPEBGH@Z; WString::Concat(ushort const *,int)
0x1800169e2  mov     ebx, eax
0x1800169e4  test    eax, eax
0x1800169e6  js      short loc_180016A26
0x1800169e8  lea     rdx, asc_180022050; "\\"
0x1800169ef  lea     rcx, [rsp+48h+var_18]; this
0x1800169f4  call    ?Concat@WString@@QEAAJPEBGH@Z; WString::Concat(ushort const *,int)
0x1800169f9  mov     ebx, eax
0x1800169fb  test    eax, eax
0x1800169fd  js      short loc_180016A26
0x1800169ff  mov     rdx, rdi; unsigned __int16 *
0x180016a02  lea     rcx, [rsp+48h+var_18]; this
0x180016a07  call    ?Concat@WString@@QEAAJPEBGH@Z; WString::Concat(ushort const *,int)
0x180016a0c  mov     ebx, eax
0x180016a0e  test    eax, eax
0x180016a10  js      short loc_180016A26
0x180016a12  mov     rcx, [rsp+48h+var_18]
0x180016a17  mov     [rsp+48h+var_28], 1
0x180016a1f  call    HMEHelpers__ModifyObjectPermissions
0x180016a24  mov     ebx, eax
0x180016a26  lea     rcx, [rsp+48h+var_18]; this
0x180016a2b  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x180016a30  mov     eax, ebx
0x180016a32  mov     rbx, [rsp+48h+arg_0]
0x180016a37  add     rsp, 40h
0x180016a3b  pop     rdi
0x180016a3c  retn
```
