# WinHvConfigureSchedulerAssistNotifications

- ea: `0x1400096b0`
- end: `0x140009744`
- name: `WinHvConfigureSchedulerAssistNotifications`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400025e0`
- `0x1400042dc`
- `0x1400096b0`

## import_xrefs

- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140009703`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x140009703`
- `ntoskrnl!ExRundownCompleted` at `0x140009712`
- `ntoskrnl!ExRundownCompleted` at `0x140009712`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x1400096f5`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x1400096f5`

## pseudocode

```c
__int64 __fastcall WinHvConfigureSchedulerAssistNotifications(__int64 a1, __int64 a2, char a3, ULONG_PTR a4)
{
  int v6; // eax
  struct _EX_RUNDOWN_REF *v7; // rbx
  unsigned int v8; // esi
  struct _EX_RUNDOWN_REF *v9; // rcx
  struct _EX_RUNDOWN_REF *v11; // [rsp+20h] [rbp-38h] BYREF

  v11 = 0;
  v6 = WinHvpReferenceVp(a1, a2, &v11);
  v7 = v11;
  v8 = v6;
  if ( v6 >= 0 )
  {
    v9 = v11 + 23;
    if ( a3 )
    {
      v11[24].Count = a4;
      ExReInitializeRundownProtection(v9);
    }
    else
    {
      ExWaitForRundownProtectionRelease(v9);
      ExRundownCompleted(v7 + 23);
      v7[24].Count = 0;
    }
  }
  if ( v7 )
    WinHvpDereferenceVp(v7);
  return v8;
}

```

## disassembly

```asm
0x1400096b0  push    rbx
0x1400096b2  push    rbp
0x1400096b3  push    rsi
0x1400096b4  push    rdi
0x1400096b5  push    r14
0x1400096b7  sub     rsp, 30h
0x1400096bb  mov     r14b, r8b
0x1400096be  mov     [rsp+58h+var_38], 0
0x1400096c7  lea     r8, [rsp+58h+var_38]
0x1400096cc  mov     rbp, r9
0x1400096cf  call    WinHvpReferenceVp
0x1400096d4  mov     rbx, [rsp+58h+var_38]
0x1400096d9  mov     esi, eax
0x1400096db  test    eax, eax
0x1400096dd  js      short loc_140009729
0x1400096df  lea     rdi, [rbx+0B8h]
0x1400096e6  mov     rcx, rdi; RunRef
0x1400096e9  test    r14b, r14b
0x1400096ec  jz      short loc_140009703
0x1400096ee  mov     [rbx+0C0h], rbp
0x1400096f5  call    cs:__imp_ExReInitializeRundownProtection
0x1400096fc  nop     dword ptr [rax+rax+00h]
0x140009701  jmp     short loc_140009729
0x140009703  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14000970a  nop     dword ptr [rax+rax+00h]
0x14000970f  mov     rcx, rdi; RunRef
0x140009712  call    cs:__imp_ExRundownCompleted
0x140009719  nop     dword ptr [rax+rax+00h]
0x14000971e  mov     qword ptr [rbx+0C0h], 0
0x140009729  test    rbx, rbx
0x14000972c  jz      short loc_140009736
0x14000972e  mov     rcx, rbx
0x140009731  call    WinHvpDereferenceVp
0x140009736  mov     eax, esi
0x140009738  add     rsp, 30h
0x14000973c  pop     r14
0x14000973e  pop     rdi
0x14000973f  pop     rsi
0x140009740  pop     rbp
0x140009741  pop     rbx
0x140009742  retn
```
