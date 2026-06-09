# PnPHelper::CHWDeviceInst::IsRemovableDevice(int *)

- ea: `0x180016260`
- end: `0x18001630c`
- name: `?IsRemovableDevice@CHWDeviceInst@PnPHelper@@QEAAJPEAH@Z`
- size: `172`
- prototype: `__int64 __fastcall(PnPHelper::CHWDeviceInst *__hidden this, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800179c0`

## callees

- `0x180016260`

## import_xrefs

- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800162ab`
- `CFGMGR32!CM_Get_DevNode_Registry_Property_ExW` at `0x1800162ab`

## pseudocode

```c
__int64 __fastcall PnPHelper::CHWDeviceInst::IsRemovableDevice(PnPHelper::CHWDeviceInst *this, int *a2)
{
  int v2; // eax
  _DWORD *v5; // rsi
  DEVINST v6; // ecx
  int v7; // eax
  ULONG pulLength; // [rsp+70h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 137);
  if ( v2 == 1 )
  {
    v5 = (_DWORD *)((char *)this + 552);
    v6 = *(_DWORD *)this;
    pulLength = 4;
    if ( !CM_Get_DevNode_Registry_Property_ExW(v6, 0x10u, 0, v5, &pulLength, 0, 0) )
    {
      v7 = (*v5 >> 2) & 1;
      *((_DWORD *)this + 137) = 2;
      *a2 = v7;
      return 0;
    }
    *((_DWORD *)this + 137) = 3;
    goto LABEL_5;
  }
  if ( v2 != 2 )
  {
LABEL_5:
    *a2 = 0;
    return 0;
  }
  *a2 = (*((_DWORD *)this + 138) >> 2) & 1;
  return 0;
}

```

## disassembly

```asm
0x180016260  push    rbx
0x180016262  push    rbp
0x180016263  push    rsi
0x180016264  push    rdi
0x180016265  sub     rsp, 48h
0x180016269  mov     eax, [rcx+224h]
0x18001626f  xor     ebp, ebp
0x180016271  mov     rdi, rdx
0x180016274  mov     rbx, rcx
0x180016277  cmp     eax, 1
0x18001627a  jnz     short loc_1800162EB
0x18001627c  lea     rsi, [rcx+228h]
0x180016283  mov     [rsp+68h+hMachine], rbp; hMachine
0x180016288  mov     ecx, [rcx]; dnDevInst
0x18001628a  lea     rax, [rsp+68h+arg_0]
0x18001628f  mov     r9, rsi; Buffer
0x180016292  mov     [rsp+68h+ulFlags], ebp; ulFlags
0x180016296  xor     r8d, r8d; pulRegDataType
0x180016299  mov     [rsp+68h+arg_0], 4
0x1800162a1  mov     edx, 10h; ulProperty
0x1800162a6  mov     [rsp+68h+pulLength], rax; pulLength
0x1800162ab  call    cs:__imp_CM_Get_DevNode_Registry_Property_ExW
0x1800162b1  test    eax, eax
0x1800162b3  jnz     short loc_1800162D4
0x1800162b5  mov     eax, [rsi]
0x1800162b7  shr     eax, 2
0x1800162ba  and     eax, 1
0x1800162bd  mov     dword ptr [rbx+224h], 2
0x1800162c7  mov     [rdi], eax
0x1800162c9  xor     eax, eax
0x1800162cb  add     rsp, 48h
0x1800162cf  pop     rdi
0x1800162d0  pop     rsi
0x1800162d1  pop     rbp
0x1800162d2  pop     rbx
0x1800162d3  retn
0x1800162d4  mov     dword ptr [rbx+224h], 3
0x1800162de  mov     [rdi], ebp
0x1800162e0  xor     eax, eax
0x1800162e2  add     rsp, 48h
0x1800162e6  pop     rdi
0x1800162e7  pop     rsi
0x1800162e8  pop     rbp
0x1800162e9  pop     rbx
0x1800162ea  retn
0x1800162eb  cmp     eax, 2
0x1800162ee  jnz     short loc_1800162DE
0x1800162f0  lea     rsi, [rcx+228h]
0x1800162f7  mov     eax, [rsi]
0x1800162f9  shr     eax, 2
0x1800162fc  and     eax, 1
0x1800162ff  mov     [rdi], eax
0x180016301  xor     eax, eax
0x180016303  add     rsp, 48h
0x180016307  pop     rdi
0x180016308  pop     rsi
0x180016309  pop     rbp
0x18001630a  pop     rbx
0x18001630b  retn
```
