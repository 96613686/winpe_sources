# WldpRemapExecutionPolicy

- ea: `0x18002e4d4`
- end: `0x18002e574`
- name: `WldpRemapExecutionPolicy`
- size: `160`
- prototype: `__int64 __fastcall(_QWORD *, int, _DWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002e5f0`
- `0x18002e8b0`
- `0x18002ecc0`
- `0x18002f2f0`

## callees

- `0x18001f038`
- `0x18002e4d4`
- `0x1800351e0`

## string_xrefs

- `0x18002e53c`: `onecore\base\ngscb\wldp\dll\canexecute.cpp`

## pseudocode

```c
__int64 __fastcall WldpRemapExecutionPolicy(_QWORD *a1, int a2, _DWORD *a3)
{
  bool v4; // zf
  __int64 v5; // rax
  int ApplicationSettingBoolean; // eax
  unsigned int v7; // ebx
  int v9; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v12; // [rsp+38h] [rbp+10h] BYREF

  v12 = a2;
  v5 = *a1 - WLDP_HOST_POWERSHELL;
  v4 = *a1 == WLDP_HOST_POWERSHELL;
  v12 = 0;
  if ( v4 )
    v5 = a1[1] - 0x5864AD470DA541AELL;
  if ( v5 )
  {
    *a3 = 0;
  }
  else
  {
    ApplicationSettingBoolean = WldpGetApplicationSettingBoolean(
                                  L"Powershell",
                                  L"BlockScriptOnPolicyFailure",
                                  (int)&v12);
    v7 = ApplicationSettingBoolean;
    if ( ApplicationSettingBoolean >= 0 )
    {
      v9 = v12;
    }
    else
    {
      if ( ApplicationSettingBoolean != -2147023728 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x163,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\canexecute.cpp",
          (const char *)(unsigned int)ApplicationSettingBoolean,
          v10);
        return v7;
      }
      v9 = 0;
    }
    *a3 = v9 == 0 ? 2 : 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18002e4d4  mov     [rsp+arg_0], rbx
0x18002e4d9  mov     [rsp+arg_8], edx
0x18002e4dd  push    rdi; int
0x18002e4de  sub     rsp, 20h
0x18002e4e2  mov     rax, [rcx]
0x18002e4e5  mov     rdi, r8
0x18002e4e8  sub     rax, cs:WLDP_HOST_POWERSHELL
0x18002e4ef  mov     [rsp+28h+arg_8], 0
0x18002e4f7  jnz     short loc_18002E504
0x18002e4f9  mov     rax, [rcx+8]
0x18002e4fd  sub     rax, cs:qword_180048C98
0x18002e504  test    rax, rax
0x18002e507  jz      short loc_18002E512
0x18002e509  mov     dword ptr [r8], 0
0x18002e510  jmp     short loc_18002E567
0x18002e512  lea     r8, [rsp+28h+arg_8]; int
0x18002e517  lea     rdx, aBlockscriptonp; "BlockScriptOnPolicyFailure"
0x18002e51e  lea     rcx, aPowershell_0; "Powershell"
0x18002e525  call    WldpGetApplicationSettingBoolean
0x18002e52a  mov     ebx, eax
0x18002e52c  test    eax, eax
0x18002e52e  jns     short loc_18002E558
0x18002e530  cmp     eax, 80070490h
0x18002e535  jz      short loc_18002E554
0x18002e537  mov     rcx, [rsp+28h]; this
0x18002e53c  lea     r8, aOnecoreBaseNgs_6; "onecore\\base\\ngscb\\wldp\\dll\\canexe"...
0x18002e543  mov     r9d, eax; char *
0x18002e546  mov     edx, 163h; void *
0x18002e54b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e550  mov     eax, ebx
0x18002e552  jmp     short loc_18002E569
0x18002e554  xor     eax, eax
0x18002e556  jmp     short loc_18002E55C
0x18002e558  mov     eax, [rsp+28h+arg_8]
0x18002e55c  neg     eax
0x18002e55e  sbb     eax, eax
0x18002e560  not     eax
0x18002e562  and     eax, 2
0x18002e565  mov     [rdi], eax
0x18002e567  xor     eax, eax
0x18002e569  mov     rbx, [rsp+28h+arg_0]
0x18002e56e  add     rsp, 20h
0x18002e572  pop     rdi
0x18002e573  retn
```
