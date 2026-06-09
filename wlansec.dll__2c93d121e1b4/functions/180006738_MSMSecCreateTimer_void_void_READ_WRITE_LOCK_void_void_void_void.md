# MSMSecCreateTimer(void * *,void *,_READ_WRITE_LOCK *,void *,void (*)(void *,void *))

- ea: `0x180006738`
- end: `0x180006816`
- name: `?MSMSecCreateTimer@@YAKPEAPEAXPEAXPEAU_READ_WRITE_LOCK@@1P6AX11@Z@Z`
- size: `222`
- prototype: `unsigned int __fastcall(void **, void *, struct _READ_WRITE_LOCK *, void *, void (*)(void *, void *))`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x18000485c`
- `0x180004c3c`
- `0x18000577c`
- `0x1800063f4`
- `0x1800065a4`

## callees

- `0x180006738`
- `0x18000892c`
- `0x180008998`

## import_xrefs

- `MobileNetworking!CreateTimer` at `0x18000677b`
- `MobileNetworking!CreateTimer` at `0x18000677b`

## pseudocode

```c
__int64 __fastcall MSMSecCreateTimer(
        void **a1,
        void *a2,
        struct _READ_WRITE_LOCK *a3,
        void *a4,
        void (*a5)(void *, void *))
{
  unsigned int Timer; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 18, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids);
  Timer = CreateTimer(a1, a2, a3, a4, a5);
  v10 = Timer;
  if ( !Timer )
    goto LABEL_3;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v10;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 19, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids, Timer);
LABEL_3:
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_DWORD *)v11 + 17) & 0x100) != 0 )
    WPP_SF_d(v11[7], 20, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180006738  push    rbx
0x18000673a  push    rbp
0x18000673b  push    rsi
0x18000673c  push    rdi
0x18000673d  push    r14
0x18000673f  sub     rsp, 30h
0x180006743  mov     rbx, r9
0x180006746  mov     rdi, r8
0x180006749  mov     rsi, rdx
0x18000674c  mov     rbp, rcx
0x18000674f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006756  lea     r14, WPP_GLOBAL_Control
0x18000675d  cmp     rcx, r14
0x180006760  jnz     short loc_1800067B0
0x180006762  mov     rax, [rsp+58h+arg_20]
0x18000676a  mov     r9, rbx
0x18000676d  mov     r8, rdi
0x180006770  mov     [rsp+58h+var_38], rax
0x180006775  mov     rdx, rsi
0x180006778  mov     rcx, rbp
0x18000677b  call    cs:__imp_CreateTimer
0x180006782  nop     dword ptr [rax+rax+00h]
0x180006787  mov     ebx, eax
0x180006789  test    eax, eax
0x18000678b  jnz     short loc_1800067D0
0x18000678d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006794  cmp     rcx, r14
0x180006797  jz      short loc_1800067A2
0x180006799  test    dword ptr [rcx+44h], 100h
0x1800067a0  jnz     short loc_1800067FC
0x1800067a2  mov     eax, ebx
0x1800067a4  add     rsp, 30h
0x1800067a8  pop     r14
0x1800067aa  pop     rdi
0x1800067ab  pop     rsi
0x1800067ac  pop     rbp
0x1800067ad  pop     rbx
0x1800067ae  retn
0x1800067b0  test    dword ptr [rcx+44h], 100h
0x1800067b7  jz      short loc_180006762
0x1800067b9  mov     rcx, [rcx+38h]
0x1800067bd  lea     r8, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids
0x1800067c4  mov     edx, 12h
0x1800067c9  call    WPP_SF_
0x1800067ce  jmp     short loc_180006762
0x1800067d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067d7  cmp     rcx, r14
0x1800067da  jz      short loc_1800067A2
0x1800067dc  test    byte ptr [rcx+44h], 1
0x1800067e0  jz      short loc_180006794
0x1800067e2  mov     rcx, [rcx+38h]
0x1800067e6  lea     r8, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids
0x1800067ed  mov     edx, 13h
0x1800067f2  mov     r9d, ebx
0x1800067f5  call    WPP_SF_d
0x1800067fa  jmp     short loc_18000678D
0x1800067fc  mov     rcx, [rcx+38h]
0x180006800  lea     r8, WPP_af9f9ec4a94e340b956c894f3cebdf2e_Traceguids
0x180006807  mov     edx, 14h
0x18000680c  mov     r9d, ebx
0x18000680f  call    WPP_SF_d
0x180006814  jmp     short loc_1800067A2
```
