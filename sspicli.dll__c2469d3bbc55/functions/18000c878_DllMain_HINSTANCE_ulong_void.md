# _DllMain(HINSTANCE__ *,ulong,void *)

- ea: `0x18000c878`
- end: `0x18000c8fd`
- name: `?_DllMain@@YAHPEAUHINSTANCE__@@KPEAX@Z`
- size: `133`
- prototype: `__int64 __fastcall(HINSTANCE hLibModule, unsigned int, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000c7f0`

## callees

- `0x18000c878`
- `0x18000c904`
- `0x18000ca24`
- `0x18000ca7c`
- `0x18000cb04`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c8d5`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c8d5`

## pseudocode

```c
__int64 __fastcall _DllMain(HINSTANCE hLibModule, int a2, __int64 a3)
{
  __int64 v6; // rcx

  if ( a2 )
  {
    if ( a2 == 1 )
    {
      qword_18003FC68 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_SspiCliTraceGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_18003FC70 = 1;
      WppInitUm();
      DisableThreadLibraryCalls(hLibModule);
      return ProcAttach(hLibModule);
    }
    else
    {
      return 1;
    }
  }
  else
  {
    WppCleanupUm(0);
    return ProcDetach(v6, a3);
  }
}

```

## disassembly

```asm
0x18000c878  mov     [rsp+arg_0], rbx
0x18000c87d  push    rdi
0x18000c87e  sub     rsp, 20h
0x18000c882  mov     rdi, rcx
0x18000c885  mov     rbx, r8
0x18000c888  xor     ecx, ecx
0x18000c88a  test    edx, edx
0x18000c88c  jz      short loc_18000C8E5
0x18000c88e  cmp     edx, 1
0x18000c891  jz      short loc_18000C898
0x18000c893  lea     eax, [rcx+1]
0x18000c896  jmp     short loc_18000C8F2
0x18000c898  lea     rax, WPP_ThisDir_CTLGUID_SspiCliTraceGuid
0x18000c89f  mov     cs:qword_18003FC68, rcx
0x18000c8a6  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000c8ad  lea     rax, WPP_MAIN_CB
0x18000c8b4  mov     cs:WPP_GLOBAL_Control, rax
0x18000c8bb  mov     cs:WPP_MAIN_CB, rcx
0x18000c8c2  mov     cs:qword_18003FC70, 1
0x18000c8cd  call    WppInitUm
0x18000c8d2  mov     rcx, rdi; hLibModule
0x18000c8d5  call    cs:__imp_DisableThreadLibraryCalls
0x18000c8db  mov     rcx, rdi
0x18000c8de  call    ProcAttach
0x18000c8e3  jmp     short loc_18000C8F2
0x18000c8e5  call    WppCleanupUm
0x18000c8ea  mov     rdx, rbx
0x18000c8ed  call    ProcDetach
0x18000c8f2  mov     rbx, [rsp+28h+arg_0]
0x18000c8f7  add     rsp, 20h
0x18000c8fb  pop     rdi
0x18000c8fc  retn
```
