# CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(bool &)

- ea: `0x1800214fc`
- end: `0x1800215af`
- name: `?HasIdleWinSATCompletedOnce@CWinSATTaskMangerTask@@AEAA_NAEA_N@Z`
- size: `179`
- prototype: `bool __fastcall(CWinSATTaskMangerTask *__hidden this, bool *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020dcc`
- `0x180021294`
- `0x1800215b8`
- `0x180021904`

## callees

- `0x18001c414`
- `0x1800214fc`
- `0x18002bc6c`

## string_xrefs

- `0x18002155e`: `base\winsat\api-dll\winsattaskmangertaskregistry.cpp`
- `0x180021557`: `cannot read the %s value from the registry`
- `0x180021548`: `IdleAssessmentCompletionCount`

## pseudocode

```c
char __fastcall CWinSATTaskMangerTask::HasIdleWinSATCompletedOnce(CWinSATTaskMangerTask *this, bool *a2)
{
  int v2; // r8d
  DWORD v5; // eax
  char result; // al
  int v7; // ecx
  char v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+50h] [rbp+18h] BYREF

  v2 = *((_DWORD *)this + 48);
  if ( v2 )
  {
    *a2 = v2 != 1;
  }
  else
  {
    v8 = 0;
    v9 = 0;
    v5 = RegHelper::ReadDWORDValue(this, a2, &v9, &v8);
    if ( v5 )
    {
      Record_Win32Error_w(
        "base\\winsat\\api-dll\\winsattaskmangertaskregistry.cpp",
        272,
        v5,
        L"cannot read the %s value from the registry",
        L"IdleAssessmentCompletionCount");
      *a2 = 0;
      result = 0;
      *((_DWORD *)this + 48) = 1;
      return result;
    }
    v7 = v9;
    if ( v8 )
      v7 = 0;
    if ( v7 )
    {
      *a2 = 1;
      *((_DWORD *)this + 48) = 2;
    }
    else
    {
      *a2 = 0;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800214fc  mov     [rsp+arg_8], rbx
0x180021501  push    rdi
0x180021502  sub     rsp, 30h
0x180021506  mov     r8d, [rcx+0C0h]
0x18002150d  mov     rbx, rdx
0x180021510  mov     rdi, rcx
0x180021513  test    r8d, r8d
0x180021516  jz      short loc_180021528
0x180021518  cmp     r8d, 1
0x18002151c  jz      short loc_180021523
0x18002151e  mov     byte ptr [rdx], 1
0x180021521  jmp     short loc_1800215A2
0x180021523  mov     byte ptr [rdx], 0
0x180021526  jmp     short loc_1800215A2
0x180021528  lea     r9, [rsp+38h+arg_0]
0x18002152d  mov     [rsp+38h+arg_0], 0
0x180021532  lea     r8, [rsp+38h+arg_10]
0x180021537  mov     [rsp+38h+arg_10], 0
0x18002153f  call    ?ReadDWORDValue@RegHelper@@SAKW4Enum@WinSATRegistryKeys@@PEBGAEAKPEA_N@Z; RegHelper::ReadDWORDValue(WinSATRegistryKeys::Enum,ushort const *,ulong &,bool *)
0x180021544  test    eax, eax
0x180021546  jz      short loc_180021580
0x180021548  lea     rcx, aIdleassessment; "IdleAssessmentCompletionCount"
0x18002154f  mov     r8d, eax
0x180021552  mov     qword ptr [rsp+38h+var_18], rcx; char
0x180021557  lea     r9, aCannotReadTheS; "cannot read the %s value from the regis"...
0x18002155e  lea     rcx, aBaseWinsatApiD_3; "base\\winsat\\api-dll\\winsattaskmanger"...
0x180021565  mov     edx, 110h
0x18002156a  call    Record_Win32Error_w
0x18002156f  mov     byte ptr [rbx], 0
0x180021572  xor     al, al
0x180021574  mov     dword ptr [rdi+0C0h], 1
0x18002157e  jmp     short loc_1800215A4
0x180021580  mov     ecx, [rsp+38h+arg_10]
0x180021584  xor     eax, eax
0x180021586  cmp     [rsp+38h+arg_0], al
0x18002158a  cmovnz  ecx, eax
0x18002158d  test    ecx, ecx
0x18002158f  jz      short loc_1800215A0
0x180021591  mov     byte ptr [rbx], 1
0x180021594  mov     dword ptr [rdi+0C0h], 2
0x18002159e  jmp     short loc_1800215A2
0x1800215a0  mov     [rbx], al
0x1800215a2  mov     al, 1
0x1800215a4  mov     rbx, [rsp+38h+arg_8]
0x1800215a9  add     rsp, 30h
0x1800215ad  pop     rdi
0x1800215ae  retn
```
