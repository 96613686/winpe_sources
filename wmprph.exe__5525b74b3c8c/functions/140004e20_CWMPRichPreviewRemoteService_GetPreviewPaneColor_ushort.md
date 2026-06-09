# CWMPRichPreviewRemoteService::GetPreviewPaneColor(ushort * *)

- ea: `0x140004e20`
- end: `0x140004e8f`
- name: `?GetPreviewPaneColor@CWMPRichPreviewRemoteService@@UEAAJPEAPEAG@Z`
- size: `111`
- prototype: `int(CWMPRichPreviewRemoteService *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x14000d91c`
- `0x14000d978`
- `0x14000e048`

## pseudocode

```c
__int64 __fastcall CWMPRichPreviewRemoteService::GetPreviewPaneColor(
        CWMPRichPreviewRemoteService *this,
        unsigned __int16 **a2)
{
  unsigned __int16 *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  __int16 v6; // [rsp+2Ch] [rbp-Ch]

  v4 = 0;
  v5 = 0;
  v6 = 0;
  WString::Sprintf(
    (WString *)&v4,
    L"#%x",
    *(_DWORD *)(*((_QWORD *)this + 4) + 72LL) & 0xFF00
  | (unsigned __int8)BYTE2(*(_DWORD *)(*((_QWORD *)this + 4) + 72LL))
  | ((unsigned __int8)*(_DWORD *)(*((_QWORD *)this + 4) + 72LL) << 16));
  WString::AllocateBSTR((WString *)&v4, a2);
  WString::DeleteString(&v4);
  return 0;
}

```

## disassembly

```asm
0x140004e20  push    rbx
0x140004e22  sub     rsp, 30h
0x140004e26  xor     eax, eax
0x140004e28  mov     rbx, rdx
0x140004e2b  mov     [rsp+38h+var_18], rax
0x140004e30  lea     rdx, asc_140011CB8; "#%x"
0x140004e37  mov     [rsp+38h+var_10], eax
0x140004e3b  mov     [rsp+38h+var_C], ax
0x140004e40  mov     rax, [rcx+20h]
0x140004e44  mov     r9d, [rax+48h]
0x140004e48  mov     eax, r9d
0x140004e4b  movzx   r8d, r9b
0x140004e4f  and     r9d, 0FF00h
0x140004e56  shl     r8d, 10h
0x140004e5a  shr     eax, 10h
0x140004e5d  movzx   ecx, al
0x140004e60  or      r8d, ecx
0x140004e63  lea     rcx, [rsp+38h+var_18]; this
0x140004e68  or      r8d, r9d
0x140004e6b  call    ?Sprintf@WString@@QEAAJPEBGZZ; WString::Sprintf(ushort const *,...)
0x140004e70  mov     rdx, rbx; unsigned __int16 **
0x140004e73  lea     rcx, [rsp+38h+var_18]; this
0x140004e78  call    ?AllocateBSTR@WString@@QEBAJPEAPEAG@Z; WString::AllocateBSTR(ushort * *)
0x140004e7d  lea     rcx, [rsp+38h+var_18]; this
0x140004e82  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x140004e87  xor     eax, eax
0x140004e89  add     rsp, 30h
0x140004e8d  pop     rbx
0x140004e8e  retn
```
