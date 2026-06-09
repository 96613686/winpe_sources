# DeleteSecurityObject

- ea: `0x180027f60`
- end: `0x180028014`
- name: `DeleteSecurityObject`
- size: `180`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000aa8c`
- `0x1800284b4`
- `0x1800287c4`

## callees

- `0x1800214a4`
- `0x1800215e8`
- `0x180027f60`

## import_xrefs

- `ntdll!RtlDeleteSecurityObject` at `0x180027f7e`
- `ntdll!RtlDeleteSecurityObject` at `0x180027f7e`

## pseudocode

```c
void __fastcall DeleteSecurityObject(_QWORD *a1)
{
  _QWORD *v1; // rbx
  NTSTATUS v3; // eax

  v1 = a1 + 2;
  if ( a1[2] )
  {
    v3 = RtlDeleteSecurityObject((PSECURITY_DESCRIPTOR *)a1 + 2);
    *v1 = 0;
    if ( v3 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids, *a1);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids,
          *a1,
          v3);
    }
  }
}

```

## disassembly

```asm
0x180027f60  mov     [rsp+arg_0], rbx
0x180027f65  push    rdi
0x180027f66  sub     rsp, 30h
0x180027f6a  lea     rbx, [rcx+10h]
0x180027f6e  mov     rdi, rcx
0x180027f71  cmp     qword ptr [rbx], 0
0x180027f75  jz      loc_180028009
0x180027f7b  mov     rcx, rbx; ObjectDescriptor
0x180027f7e  call    cs:__imp_RtlDeleteSecurityObject
0x180027f84  mov     qword ptr [rbx], 0
0x180027f8b  test    eax, eax
0x180027f8d  jns     short loc_180027FCF
0x180027f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f96  lea     rdx, WPP_GLOBAL_Control
0x180027f9d  cmp     rcx, rdx
0x180027fa0  jz      short loc_180028009
0x180027fa2  test    dword ptr [rcx+1Ch], 200h
0x180027fa9  jz      short loc_180028009
0x180027fab  cmp     byte ptr [rcx+19h], 1
0x180027faf  jb      short loc_180028009
0x180027fb1  mov     r9, [rdi]
0x180027fb4  lea     r8, WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids
0x180027fbb  mov     rcx, [rcx+10h]
0x180027fbf  mov     edx, 0Ch
0x180027fc4  mov     [rsp+38h+var_18], eax
0x180027fc8  call    WPP_SF_Sd
0x180027fcd  jmp     short loc_180028009
0x180027fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180027fd6  lea     rdx, WPP_GLOBAL_Control
0x180027fdd  cmp     rcx, rdx
0x180027fe0  jz      short loc_180028009
0x180027fe2  test    dword ptr [rcx+1Ch], 200h
0x180027fe9  jz      short loc_180028009
0x180027feb  cmp     byte ptr [rcx+19h], 2
0x180027fef  jb      short loc_180028009
0x180027ff1  mov     r9, [rdi]
0x180027ff4  lea     r8, WPP_ddde71427faa336ad73aca8248c70f7d_Traceguids
0x180027ffb  mov     rcx, [rcx+10h]
0x180027fff  mov     edx, 0Dh
0x180028004  call    WPP_SF_S
0x180028009  mov     rbx, [rsp+38h+arg_0]
0x18002800e  add     rsp, 30h
0x180028012  pop     rdi
0x180028013  retn
```
