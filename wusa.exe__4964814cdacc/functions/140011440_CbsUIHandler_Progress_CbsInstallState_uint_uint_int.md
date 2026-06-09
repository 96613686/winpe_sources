# CbsUIHandler::Progress(_CbsInstallState,uint,uint,int *)

- ea: `0x140011440`
- end: `0x140011493`
- name: `?Progress@CbsUIHandler@@UEAAJW4_CbsInstallState@@IIPEAH@Z`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x14000f240`

## pseudocode

```c
__int64 __fastcall CbsUIHandler::Progress(__int64 a1, __int64 a2, __int64 a3, int a4, _DWORD *a5)
{
  *a5 = (dword_1400201AC != 0) + 1;
  WusaPostMessage(0x406u, (int)((double)(int)a3 / (double)a4 * 100.0), a3);
  return 0;
}

```

## disassembly

```asm
0x140011440  sub     rsp, 28h
0x140011444  mov     eax, cs:dword_1400201AC
0x14001144a  xorps   xmm1, xmm1
0x14001144d  neg     eax
0x14001144f  xorps   xmm0, xmm0
0x140011452  mov     rax, [rsp+28h+arg_20]
0x140011457  sbb     ecx, ecx
0x140011459  neg     ecx
0x14001145b  inc     ecx
0x14001145d  mov     [rax], ecx
0x14001145f  mov     ecx, 406h; Msg
0x140011464  mov     eax, r8d
0x140011467  cvtsi2sd xmm1, rax
0x14001146c  mov     eax, r9d
0x14001146f  cvtsi2sd xmm0, rax
0x140011474  divsd   xmm1, xmm0
0x140011478  mulsd   xmm1, cs:__real@4059000000000000
0x140011480  cvttsd2si eax, xmm1
0x140011484  movsxd  rdx, eax; wParam
0x140011487  call    ?WusaPostMessage@@YAXI_K_J@Z; WusaPostMessage(uint,unsigned __int64,__int64)
0x14001148c  xor     eax, eax
0x14001148e  add     rsp, 28h
0x140011492  retn
```
