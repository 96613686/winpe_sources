# CUwfStaticConfiguration::set_UwfEnabled(bool)

- ea: `0x18000d040`
- end: `0x18000d0d3`
- name: `?set_UwfEnabled@CUwfStaticConfiguration@@QEAAJ_N@Z`
- size: `147`
- prototype: `__int64 __fastcall(CUwfStaticConfiguration *this, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180019a30`

## callees

- `0x180006144`
- `0x180009688`
- `0x18000a150`
- `0x18000d040`
- `0x18000e884`

## pseudocode

```c
__int64 __fastcall CUwfStaticConfiguration::set_UwfEnabled(CUwfStaticConfiguration *this, unsigned __int8 a2)
{
  bool v2; // zf
  CUwfConfiguration **v3; // rbx
  int updated; // ecx
  int v6; // eax
  HKEY v7; // r8
  bool v8; // sf
  bool v10; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_BYTE *)this + 9) == 0;
  v3 = (CUwfConfiguration **)((char *)this + 32);
  v10 = 0;
  if ( !v2 )
  {
    updated = -2147024891;
LABEL_11:
    *((_DWORD *)*v3 + 4) = updated;
    return (unsigned int)updated;
  }
  updated = CUwfConfiguration::UpdateDWORDValue(
              *v3,
              (CUwfStaticConfiguration *)((char *)this + 16),
              L"UWFEnabled",
              a2,
              1);
  if ( updated < 0 )
    goto LABEL_11;
  v6 = CheckEduRestartPolicyEnabled(&v10);
  updated = v6;
  if ( v6 < 0 )
    goto LABEL_11;
  if ( !v10 )
  {
    if ( a2 )
    {
      updated = CUwfStaticConfiguration::SetBackgroundTasksDisabled((CUwfStaticConfiguration *)(unsigned int)v6, 1u);
      v8 = updated < 0;
      goto LABEL_10;
    }
    updated = CUwfStaticConfiguration::ClearBackgroundTasksDisabled(
                (CUwfStaticConfiguration *)(unsigned int)v6,
                0xEu,
                v7);
  }
  v8 = updated < 0;
LABEL_10:
  if ( v8 )
    goto LABEL_11;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18000d040  mov     [rsp+arg_8], rbx
0x18000d045  push    rdi
0x18000d046  sub     rsp, 30h
0x18000d04a  cmp     byte ptr [rcx+9], 0
0x18000d04e  lea     rbx, [rcx+20h]
0x18000d052  movzx   edi, dl
0x18000d055  mov     [rsp+38h+arg_0], 0
0x18000d05a  jz      short loc_18000D063
0x18000d05c  mov     ecx, 80070005h
0x18000d061  jmp     short loc_18000D0C0
0x18000d063  lea     rdx, [rcx+10h]; struct CUwfRegKey *
0x18000d067  mov     [rsp+38h+var_18], 1; bool
0x18000d06c  mov     rcx, [rbx]; this
0x18000d06f  lea     r8, aUwfenabled; "UWFEnabled"
0x18000d076  mov     r9d, edi; unsigned int
0x18000d079  call    ?UpdateDWORDValue@CUwfConfiguration@@QEAAJAEAVCUwfRegKey@@PEBGK_N@Z; CUwfConfiguration::UpdateDWORDValue(CUwfRegKey &,ushort const *,ulong,bool)
0x18000d07e  mov     ecx, eax
0x18000d080  test    eax, eax
0x18000d082  js      short loc_18000D0C0
0x18000d084  lea     rcx, [rsp+38h+arg_0]; bool *
0x18000d089  call    ?CheckEduRestartPolicyEnabled@@YAJPEA_N@Z; CheckEduRestartPolicyEnabled(bool *)
0x18000d08e  mov     ecx, eax; this
0x18000d090  test    eax, eax
0x18000d092  js      short loc_18000D0C0
0x18000d094  cmp     [rsp+38h+arg_0], 0
0x18000d099  jnz     short loc_18000D0BC
0x18000d09b  test    dil, dil
0x18000d09e  jz      short loc_18000D0B0
0x18000d0a0  mov     edx, 1; unsigned int
0x18000d0a5  call    ?SetBackgroundTasksDisabled@CUwfStaticConfiguration@@AEAAJK@Z; CUwfStaticConfiguration::SetBackgroundTasksDisabled(ulong)
0x18000d0aa  mov     ecx, eax
0x18000d0ac  test    eax, eax
0x18000d0ae  jmp     short loc_18000D0BE
0x18000d0b0  mov     edx, 0Eh; unsigned int
0x18000d0b5  call    ?ClearBackgroundTasksDisabled@CUwfStaticConfiguration@@AEAAJK@Z; CUwfStaticConfiguration::ClearBackgroundTasksDisabled(ulong)
0x18000d0ba  mov     ecx, eax
0x18000d0bc  test    ecx, ecx
0x18000d0be  jns     short loc_18000D0C6
0x18000d0c0  mov     rax, [rbx]
0x18000d0c3  mov     [rax+10h], ecx
0x18000d0c6  mov     rbx, [rsp+38h+arg_8]
0x18000d0cb  mov     eax, ecx
0x18000d0cd  add     rsp, 30h
0x18000d0d1  pop     rdi
0x18000d0d2  retn
```
