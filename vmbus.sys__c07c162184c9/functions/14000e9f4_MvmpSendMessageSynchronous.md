# MvmpSendMessageSynchronous

- ea: `0x14000e9f4`
- end: `0x14000eaa1`
- name: `MvmpSendMessageSynchronous`
- size: `173`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d300`
- `0x14000d410`
- `0x14000d620`
- `0x14000d704`
- `0x14000d910`
- `0x14000da50`
- `0x14000dde8`
- `0x14000df90`

## callees

- `0x14000b3e0`
- `0x14000e7d4`
- `0x14000e9f4`
- `0x140017240`
- `0x140017540`

## pseudocode

```c
char __fastcall MvmpSendMessageSynchronous(__int64 a1, int a2, unsigned int *a3)
{
  _DWORD *v3; // rbx
  int v7; // eax
  int v8; // r9d
  __int16 v9; // ax

  v3 = *(_DWORD **)a1;
  memset(*(void **)a1, 0, 0x100u);
  v7 = *(_DWORD *)(a1 + 168) & 0xFFFFFF;
  v3[2] = 1;
  *v3 = v7;
  v3[3] = *a3;
  memmove(v3 + 4, a3 + 1, *a3);
  while ( 1 )
  {
    v9 = MvmpIssueHypercall(a1, a2, 92, v8, 0, *(_QWORD *)(a1 + 8));
    switch ( v9 )
    {
      case 0:
        return 1;
      case 2:
        goto LABEL_6;
      case 18:
        if ( *(_DWORD *)(a1 + 216) == 1 )
        {
LABEL_6:
          *(_DWORD *)(a1 + 208) = 8;
          return 0;
        }
        break;
      case 19:
        break;
      default:
        goto LABEL_6;
    }
    MvmStall();
  }
}

```

## disassembly

```asm
0x14000e9f4  push    rbx
0x14000e9f6  push    rbp
0x14000e9f7  push    rsi
0x14000e9f8  push    rdi
0x14000e9f9  sub     rsp, 48h
0x14000e9fd  mov     rbx, [rcx]
0x14000ea00  mov     rdi, r8
0x14000ea03  mov     rbp, rdx
0x14000ea06  mov     rsi, rcx
0x14000ea09  mov     rcx, rbx; void *
0x14000ea0c  xor     edx, edx; Val
0x14000ea0e  mov     r8d, 100h; Size
0x14000ea14  call    memset
0x14000ea19  mov     eax, [rsi+0A8h]
0x14000ea1f  lea     rdx, [rdi+4]; Src
0x14000ea23  and     eax, 0FFFFFFh
0x14000ea28  mov     dword ptr [rbx+8], 1
0x14000ea2f  mov     [rbx], eax
0x14000ea31  lea     rcx, [rbx+10h]; void *
0x14000ea35  mov     eax, [rdi]
0x14000ea37  mov     [rbx+0Ch], eax
0x14000ea3a  mov     r8d, [rdi]; Size
0x14000ea3d  call    memmove
0x14000ea42  mov     rax, [rsi+8]
0x14000ea46  mov     r8d, 5Ch ; '\'
0x14000ea4c  mov     [rsp+68h+var_40], rax
0x14000ea51  mov     rdx, rbp
0x14000ea54  mov     rcx, rsi
0x14000ea57  mov     [rsp+68h+var_48], 0
0x14000ea5c  call    MvmpIssueHypercall
0x14000ea61  movzx   ecx, ax
0x14000ea64  test    ecx, ecx
0x14000ea66  jz      short loc_14000EA95
0x14000ea68  sub     ecx, 2
0x14000ea6b  jz      short loc_14000EA77
0x14000ea6d  sub     ecx, 10h
0x14000ea70  jz      short loc_14000EA85
0x14000ea72  cmp     ecx, 1
0x14000ea75  jz      short loc_14000EA8E
0x14000ea77  mov     dword ptr [rsi+0D0h], 8
0x14000ea81  xor     al, al
0x14000ea83  jmp     short loc_14000EA97
0x14000ea85  cmp     dword ptr [rsi+0D8h], 1
0x14000ea8c  jz      short loc_14000EA77
0x14000ea8e  call    MvmStall
0x14000ea93  jmp     short loc_14000EA42
0x14000ea95  mov     al, 1
0x14000ea97  add     rsp, 48h
0x14000ea9b  pop     rdi
0x14000ea9c  pop     rsi
0x14000ea9d  pop     rbp
0x14000ea9e  pop     rbx
0x14000ea9f  retn
```
