# CWerService::SvcReportStorePruneUserStore(_WERSVC_MSG *,_WERSVC_MSG *)

- ea: `0x18001a5a0`
- end: `0x18001a69e`
- name: `?SvcReportStorePruneUserStore@CWerService@@AEAAJPEAU_WERSVC_MSG@@0@Z`
- size: `254`
- prototype: `__int64 __fastcall(CWerService *__hidden this, struct _WERSVC_MSG *, struct _WERSVC_MSG *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180014fa4`

## callees

- `0x180011ef8`
- `0x18001a5a0`

## import_xrefs

- `wer!WerpOpenMachineQueue` at `0x18001a604`
- `wer!WerpOpenMachineQueue` at `0x18001a604`
- `wer!WerpPruneStore` at `0x18001a635`
- `wer!WerpPruneStore` at `0x18001a635`
- `wer!WerpCloseStore` at `0x18001a66d`
- `wer!WerpCloseStore` at `0x18001a66d`
- `wer!WerpOpenMachineArchive` at `0x18001a5c5`
- `wer!WerpOpenMachineArchive` at `0x18001a5c5`

## pseudocode

```c
__int64 __fastcall CWerService::SvcReportStorePruneUserStore(
        CWerService *this,
        struct _WERSVC_MSG *a2,
        struct _WERSVC_MSG *a3)
{
  bool v3; // zf
  int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  CWerService *v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = this;
  v3 = *((_DWORD *)a2 + 12) == 0;
  v10 = 0;
  if ( !v3 )
  {
    v5 = WerpOpenMachineArchive(&v10);
    if ( v5 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 112;
LABEL_6:
        WPP_SF_d(v6[2], v7, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids, (unsigned int)v5);
        goto LABEL_16;
      }
      goto LABEL_16;
    }
LABEL_11:
    v5 = WerpPruneStore(v10);
    if ( v5 >= 0 )
    {
      v5 = 0;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v7 = 114;
        goto LABEL_6;
      }
    }
    goto LABEL_16;
  }
  v5 = WerpOpenMachineQueue(&v10);
  if ( v5 >= 0 )
    goto LABEL_11;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 113;
    goto LABEL_6;
  }
LABEL_16:
  if ( v10 )
    WerpCloseStore();
  *((_DWORD *)a3 + 11) = v5;
  if ( v5 < 0 )
  {
    v8 = -1073741823;
  }
  else
  {
    *((_QWORD *)a3 + 7) = 0;
    v8 = -1073741824;
  }
  *((_DWORD *)a3 + 10) = v8;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001a5a0  mov     rax, rsp
0x18001a5a3  mov     [rax+10h], rbx
0x18001a5a7  mov     [rax+8], rcx
0x18001a5ab  push    rdi
0x18001a5ac  sub     rsp, 20h
0x18001a5b0  cmp     dword ptr [rdx+30h], 0
0x18001a5b4  lea     rcx, [rax+8]
0x18001a5b8  mov     rdi, r8
0x18001a5bb  mov     qword ptr [rax+8], 0
0x18001a5c3  jz      short loc_18001A604
0x18001a5c5  call    cs:__imp_WerpOpenMachineArchive
0x18001a5cb  mov     ebx, eax
0x18001a5cd  test    eax, eax
0x18001a5cf  jns     short loc_18001A630
0x18001a5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5d8  lea     rax, WPP_GLOBAL_Control
0x18001a5df  cmp     rcx, rax
0x18001a5e2  jz      short loc_18001A663
0x18001a5e4  test    byte ptr [rcx+1Ch], 1
0x18001a5e8  jz      short loc_18001A663
0x18001a5ea  mov     edx, 70h ; 'p'
0x18001a5ef  mov     rcx, [rcx+10h]
0x18001a5f3  lea     r8, WPP_1b6e0a3721613836d8ea9c50d6cd3648_Traceguids
0x18001a5fa  mov     r9d, ebx
0x18001a5fd  call    WPP_SF_d
0x18001a602  jmp     short loc_18001A663
0x18001a604  call    cs:__imp_WerpOpenMachineQueue
0x18001a60a  mov     ebx, eax
0x18001a60c  test    eax, eax
0x18001a60e  jns     short loc_18001A630
0x18001a610  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a617  lea     rax, WPP_GLOBAL_Control
0x18001a61e  cmp     rcx, rax
0x18001a621  jz      short loc_18001A663
0x18001a623  test    byte ptr [rcx+1Ch], 1
0x18001a627  jz      short loc_18001A663
0x18001a629  mov     edx, 71h ; 'q'
0x18001a62e  jmp     short loc_18001A5EF
0x18001a630  mov     rcx, [rsp+28h+arg_0]
0x18001a635  call    cs:__imp_WerpPruneStore
0x18001a63b  mov     ebx, eax
0x18001a63d  test    eax, eax
0x18001a63f  jns     short loc_18001A661
0x18001a641  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a648  lea     rax, WPP_GLOBAL_Control
0x18001a64f  cmp     rcx, rax
0x18001a652  jz      short loc_18001A663
0x18001a654  test    byte ptr [rcx+1Ch], 1
0x18001a658  jz      short loc_18001A663
0x18001a65a  mov     edx, 72h ; 'r'
0x18001a65f  jmp     short loc_18001A5EF
0x18001a661  xor     ebx, ebx
0x18001a663  mov     rcx, [rsp+28h+arg_0]
0x18001a668  test    rcx, rcx
0x18001a66b  jz      short loc_18001A673
0x18001a66d  call    cs:__imp_WerpCloseStore
0x18001a673  mov     [rdi+2Ch], ebx
0x18001a676  test    ebx, ebx
0x18001a678  js      short loc_18001A689
0x18001a67a  mov     qword ptr [rdi+38h], 0
0x18001a682  mov     eax, 0C0000000h
0x18001a687  jmp     short loc_18001A68E
0x18001a689  mov     eax, 0C0000001h
0x18001a68e  mov     [rdi+28h], eax
0x18001a691  mov     eax, ebx
0x18001a693  mov     rbx, [rsp+28h+arg_8]
0x18001a698  add     rsp, 20h
0x18001a69c  pop     rdi
0x18001a69d  retn
```
