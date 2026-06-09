# SpGetInfo(_SecPkgInfoW *)

- ea: `0x180017960`
- end: `0x1800179c9`
- name: `?SpGetInfo@@YAJPEAU_SecPkgInfoW@@@Z`
- size: `105`
- prototype: `__int64 __fastcall(struct _SecPkgInfoW *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001627c`
- `0x180017960`

## string_xrefs

- `0x1800179a9`: `TS Service Security Package`

## pseudocode

```c
__int64 __fastcall SpGetInfo(struct _SecPkgInfoW *a1)
{
  __int64 result; // rax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_76ddc22de44c3ba40c130d8634e0bbce_Traceguids);
  *(_DWORD *)&a1->wVersion = 1441793;
  a1->Name = L"TSSSP";
  a1->Comment = L"TS Service Security Package";
  result = 0;
  a1->fCapabilities = 8454704;
  a1->cbMaxToken = 13000;
  return result;
}

```

## disassembly

```asm
0x180017960  push    rbx
0x180017962  sub     rsp, 20h
0x180017966  mov     rbx, rcx
0x180017969  mov     rcx, cs:WPP_GLOBAL_Control
0x180017970  lea     rax, WPP_GLOBAL_Control
0x180017977  cmp     rcx, rax
0x18001797a  jz      short loc_180017997
0x18001797c  test    byte ptr [rcx+1Ch], 20h
0x180017980  jz      short loc_180017997
0x180017982  mov     rcx, [rcx+10h]
0x180017986  lea     r8, WPP_76ddc22de44c3ba40c130d8634e0bbce_Traceguids
0x18001798d  mov     edx, 0Ch
0x180017992  call    WPP_SF_
0x180017997  lea     rax, aTsssp; "TSSSP"
0x18001799e  mov     dword ptr [rbx+4], 160001h
0x1800179a5  mov     [rbx+10h], rax
0x1800179a9  lea     rax, aTsServiceSecur; "TS Service Security Package"
0x1800179b0  mov     [rbx+18h], rax
0x1800179b4  xor     eax, eax
0x1800179b6  mov     dword ptr [rbx], 810230h
0x1800179bc  mov     dword ptr [rbx+8], 32C8h
0x1800179c3  add     rsp, 20h
0x1800179c7  pop     rbx
0x1800179c8  retn
```
