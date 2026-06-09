# CPxeRogueDetection::SetAuthState(int)

- ea: `0x18000f8b8`
- end: `0x18000f94c`
- name: `?SetAuthState@CPxeRogueDetection@@AEAAXH@Z`
- size: `148`
- prototype: `void __fastcall(CPxeRogueDetection *__hidden this, int)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000abe4`
- `0x18000adf8`
- `0x18000c494`
- `0x18000ea3c`
- `0x1800104f4`

## callees

- `0x180002a30`
- `0x18000f8b8`

## import_xrefs

- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000f931`
- `WdsCommonLib!?Log@CEventLog@@QEAAKKHZZ` at `0x18000f931`

## pseudocode

```c
void __fastcall CPxeRogueDetection::SetAuthState(CPxeRogueDetection *this, int a2)
{
  const wchar_t *v4; // r8
  const wchar_t *v5; // r9
  unsigned int v6; // edx

  if ( a2 != *((_DWORD *)this + 13) )
  {
    v4 = L"Authorized";
    v5 = L"Authorized";
    if ( !a2 )
      v5 = L"Not Authorized";
    if ( !*((_DWORD *)this + 13) )
      v4 = L"Not Authorized";
    Trace(0x20000u, L"Rogue Detection: Authorization State Changed. Old=%s, New=%s", v4, v5);
    if ( a2 )
    {
      if ( *((_DWORD *)this + 16) )
        v6 = 1090978569;
      else
        v6 = 1090978561;
    }
    else
    {
      v6 = -1056505080;
      if ( !*((_DWORD *)this + 12) )
        v6 = -1056505086;
    }
    CEventLog::Log((CEventLog *)qword_18001CC40, v6, 0, 0);
    *((_DWORD *)this + 13) = a2;
  }
}

```

## disassembly

```asm
0x18000f8b8  mov     [rsp+arg_0], rbx
0x18000f8bd  push    rdi
0x18000f8be  sub     rsp, 20h
0x18000f8c2  mov     edi, edx
0x18000f8c4  mov     rbx, rcx
0x18000f8c7  cmp     edx, [rcx+34h]
0x18000f8ca  jz      short loc_18000F940
0x18000f8cc  test    edx, edx
0x18000f8ce  lea     rax, aNotAuthorized; "Not Authorized"
0x18000f8d5  lea     r8, aAuthorized; "Authorized"
0x18000f8dc  mov     r9, r8
0x18000f8df  lea     rdx, aRogueDetection_3; "Rogue Detection: Authorization State Ch"...
0x18000f8e6  cmovz   r9, rax
0x18000f8ea  cmp     dword ptr [rcx+34h], 0
0x18000f8ee  mov     ecx, 20000h; unsigned int
0x18000f8f3  cmovz   r8, rax
0x18000f8f7  call    ?Trace@@YAXKPEBGZZ; Trace(ulong,ushort const *,...)
0x18000f8fc  xor     r9d, r9d
0x18000f8ff  lea     rcx, qword_18001CC40
0x18000f906  xor     r8d, r8d
0x18000f909  test    edi, edi
0x18000f90b  jz      short loc_18000F921
0x18000f90d  cmp     [rbx+40h], r8d
0x18000f911  jz      short loc_18000F91A
0x18000f913  mov     edx, 41070309h
0x18000f918  jmp     short loc_18000F931
0x18000f91a  mov     edx, 41070301h
0x18000f91f  jmp     short loc_18000F931
0x18000f921  cmp     dword ptr [rbx+30h], 0
0x18000f925  mov     edx, 0C1070308h
0x18000f92a  jnz     short loc_18000F931
0x18000f92c  mov     edx, 0C1070302h
0x18000f931  call    cs:__imp_?Log@CEventLog@@QEAAKKHZZ; CEventLog::Log(ulong,int,...)
0x18000f938  nop     dword ptr [rax+rax+00h]
0x18000f93d  mov     [rbx+34h], edi
0x18000f940  mov     rbx, [rsp+28h+arg_0]
0x18000f945  add     rsp, 20h
0x18000f949  pop     rdi
0x18000f94a  retn
```
