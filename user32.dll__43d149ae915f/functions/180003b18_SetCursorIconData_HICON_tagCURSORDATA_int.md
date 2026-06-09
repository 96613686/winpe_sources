# _SetCursorIconData(HICON__ *,tagCURSORDATA *,int)

- ea: `0x180003b18`
- end: `0x180003bd6`
- name: `?_SetCursorIconData@@YAHPEAUHICON__@@PEAUtagCURSORDATA@@H@Z`
- size: `190`
- prototype: `__int64 __fastcall(HICON, struct tagCURSORDATA *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001218`
- `0x180003034`
- `0x180003c60`
- `0x18005c5e8`

## callees

- `0x180003b18`

## import_xrefs

- `win32u!NtUserSetCursorIconDataEx` at `0x180003b98`
- `win32u!NtUserSetCursorIconDataEx` at `0x180003b98`
- `ntdll!RtlInitUnicodeString` at `0x180003b60`
- `ntdll!RtlInitUnicodeString` at `0x180003bca`
- `ntdll!RtlInitUnicodeString` at `0x180003b60`
- `ntdll!RtlInitUnicodeString` at `0x180003bca`
- `GDI32!GdiTrackHDelete` at `0x180003ba8`
- `GDI32!GdiTrackHDelete` at `0x180003bb2`
- `GDI32!GdiTrackHDelete` at `0x180003ba8`
- `GDI32!GdiTrackHDelete` at `0x180003bb2`

## pseudocode

```c
__int64 __fastcall _SetCursorIconData(HICON a1, struct tagCURSORDATA *a2, int a3)
{
  const WCHAR *v4; // rdx
  WCHAR *v7; // rcx
  struct _UNICODE_STRING *v8; // r8
  unsigned int v9; // edi
  struct _UNICODE_STRING v11; // [rsp+30h] [rbp-48h] BYREF
  __int128 v12; // [rsp+40h] [rbp-38h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-28h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+60h] [rbp-18h]
  __int64 v15; // [rsp+68h] [rbp-10h]

  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v4 = (const WCHAR *)*((_QWORD *)a2 + 1);
  p_DestinationString = &DestinationString;
  v15 = 0;
  v11 = 0;
  v12 = 0;
  RtlInitUnicodeString(&DestinationString, v4);
  v7 = *(WCHAR **)a2;
  v8 = &v11;
  DWORD2(v12) = 0;
  *(_QWORD *)&v12 = &v11;
  if ( ((unsigned __int64)v7 & 0xFFFFFFFFFFFF0000uLL) != 0 )
  {
    RtlInitUnicodeString(&v11, v7);
    v8 = (struct _UNICODE_STRING *)v12;
  }
  else
  {
    v11.Buffer = v7;
    *(_DWORD *)&v11.Length = 0;
  }
  v9 = NtUserSetCursorIconDataEx(a1, p_DestinationString, v8, a2, a3);
  if ( v9 )
  {
    GdiTrackHDelete(*((_QWORD *)a2 + 4));
    GdiTrackHDelete(*((_QWORD *)a2 + 5));
  }
  return v9;
}

```

## disassembly

```asm
0x180003b18  push    rbp
0x180003b1a  push    rbx
0x180003b1b  push    rsi
0x180003b1c  push    rdi
0x180003b1d  mov     rbp, rsp
0x180003b20  sub     rsp, 78h
0x180003b24  xorps   xmm0, xmm0
0x180003b27  mov     qword ptr [rbp+DestinationString.Length], 0
0x180003b2f  mov     rbx, rdx
0x180003b32  mov     [rbp+DestinationString.Buffer], 0
0x180003b3a  mov     rdx, [rdx+8]; SourceString
0x180003b3e  lea     rax, [rbp+DestinationString]
0x180003b42  mov     rsi, rcx
0x180003b45  mov     [rbp+var_18], rax
0x180003b49  lea     rcx, [rbp+DestinationString]; DestinationString
0x180003b4d  mov     [rbp+var_10], 0
0x180003b55  movups  xmmword ptr [rbp+var_48.Length], xmm0
0x180003b59  mov     edi, r8d
0x180003b5c  movups  [rbp+var_38], xmm0
0x180003b60  call    cs:__imp_RtlInitUnicodeString
0x180003b66  mov     rcx, [rbx]
0x180003b69  lea     r8, [rbp+var_48]
0x180003b6d  mov     dword ptr [rbp+var_38+8], 0
0x180003b74  mov     qword ptr [rbp+var_38], r8
0x180003b78  test    rcx, 0FFFFFFFFFFFF0000h
0x180003b7f  jnz     short loc_180003BC3
0x180003b81  xor     eax, eax
0x180003b83  mov     [rbp+var_48.Buffer], rcx
0x180003b87  mov     dword ptr [rbp+var_48.Length], eax
0x180003b8a  mov     rdx, [rbp+var_18]
0x180003b8e  mov     r9, rbx
0x180003b91  mov     rcx, rsi
0x180003b94  mov     [rsp+78h+var_58], edi
0x180003b98  call    cs:__imp_NtUserSetCursorIconDataEx
0x180003b9e  mov     edi, eax
0x180003ba0  test    eax, eax
0x180003ba2  jz      short loc_180003BB8
0x180003ba4  mov     rcx, [rbx+20h]
0x180003ba8  call    cs:__imp_GdiTrackHDelete
0x180003bae  mov     rcx, [rbx+28h]
0x180003bb2  call    cs:__imp_GdiTrackHDelete
0x180003bb8  mov     eax, edi
0x180003bba  add     rsp, 78h
0x180003bbe  pop     rdi
0x180003bbf  pop     rsi
0x180003bc0  pop     rbx
0x180003bc1  pop     rbp
0x180003bc2  retn
0x180003bc3  mov     rdx, rcx; SourceString
0x180003bc6  lea     rcx, [rbp+var_48]; DestinationString
0x180003bca  call    cs:__imp_RtlInitUnicodeString
0x180003bd0  mov     r8, qword ptr [rbp+var_38]
0x180003bd4  jmp     short loc_180003B8A
```
