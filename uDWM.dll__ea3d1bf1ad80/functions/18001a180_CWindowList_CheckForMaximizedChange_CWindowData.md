# CWindowList::CheckForMaximizedChange(CWindowData *)

- ea: `0x18001a180`
- end: `0x18001a2f6`
- name: `?CheckForMaximizedChange@CWindowList@@AEAAXPEAVCWindowData@@@Z`
- size: `374`
- prototype: `void __fastcall(CWindowList *__hidden this, struct CWindowData *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001c070`
- `0x1800469d8`
- `0x18007d110`

## callees

- `0x18001a180`
- `0x18002d478`
- `0x18004f008`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18001a25f`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18001a25f`
- `ntdll!RtlInsertElementGenericTable` at `0x18001a28a`
- `ntdll!RtlInsertElementGenericTable` at `0x18001a28a`
- `ntdll!RtlLookupElementGenericTable` at `0x18001a22c`
- `ntdll!RtlLookupElementGenericTable` at `0x18001a22c`
- `ntdll!RtlIsGenericTableEmpty` at `0x18001a1b3`
- `ntdll!RtlIsGenericTableEmpty` at `0x18001a1e8`
- `ntdll!RtlIsGenericTableEmpty` at `0x18001a1b3`
- `ntdll!RtlIsGenericTableEmpty` at `0x18001a1e8`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001a24b`
- `ntdll!RtlDeleteElementGenericTable` at `0x18001a24b`
- `USER32!PostMessageW` at `0x18001a2ee`
- `USER32!PostMessageW` at `0x18001a2ee`

## pseudocode

```c
void __fastcall CWindowList::CheckForMaximizedChange(CWindowList *this, struct CWindowData *a2)
{
  char v3; // bp
  bool v5; // di
  char v6; // r14
  unsigned __int8 v7; // di
  struct CWindowData **v8; // rax
  struct _LIST_ENTRY *WindowListForDesktop; // rsi
  struct _LIST_ENTRY *i; // rbx
  struct CWindowData *Buffer; // [rsp+60h] [rbp+8h] BYREF

  v3 = *((_BYTE *)a2 + 737);
  v5 = (*((_DWORD *)a2 + 29) & 0x11000000) == 0x11000000 && *((_QWORD *)a2 + 4);
  v6 = RtlIsGenericTableEmpty((PRTL_GENERIC_TABLE)((char *)this + 424)) == 0;
  *((_BYTE *)a2 + 737) &= ~2u;
  *((_BYTE *)a2 + 737) |= 2 * v5;
  if ( v5 )
  {
    if ( (v3 & 2) == 0 )
    {
      Buffer = a2;
      RtlInsertElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 424), &Buffer, 8u, 0);
      goto LABEL_5;
    }
  }
  else if ( (v3 & 2) == 0 )
  {
    goto LABEL_5;
  }
  if ( !v5 )
  {
    Buffer = a2;
    v8 = (struct CWindowData **)RtlLookupElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 424), &Buffer);
    if ( v8 )
    {
      Buffer = *v8;
      if ( !RtlDeleteElementGenericTable((PRTL_GENERIC_TABLE)((char *)this + 424), &Buffer) )
        RaiseFailFastException(0, 0, 1u);
    }
  }
LABEL_5:
  v7 = RtlIsGenericTableEmpty((PRTL_GENERIC_TABLE)((char *)this + 424)) == 0;
  if ( v6 != v7 )
  {
    WindowListForDesktop = CWindowList::GetWindowListForDesktop(this, *((_QWORD *)a2 + 17));
    *((_BYTE *)CDesktopManager::s_pDesktopManagerInstance + 21) = v7;
    for ( i = WindowListForDesktop->Flink; i != WindowListForDesktop; i = i->Flink )
    {
      if ( (BYTE1(i[46].Flink) & 8) != 0 )
      {
        CWindowData::OnColorizationUpdated((CWindowData *)i);
        PostMessageW((HWND)i[2].Blink, 0x321u, v7, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x18001a180  push    rbx
0x18001a182  push    rbp
0x18001a183  push    rsi
0x18001a184  push    rdi
0x18001a185  push    r14
0x18001a187  push    r15
0x18001a189  sub     rsp, 28h
0x18001a18d  mov     eax, [rdx+74h]
0x18001a190  mov     rbx, rdx
0x18001a193  movzx   ebp, byte ptr [rdx+2E1h]
0x18001a19a  and     eax, 11000000h
0x18001a19f  mov     r15, rcx
0x18001a1a2  cmp     eax, 11000000h
0x18001a1a7  jz      short loc_18001A20A
0x18001a1a9  xor     dil, dil
0x18001a1ac  add     rcx, 1A8h; Table
0x18001a1b3  call    cs:__imp_RtlIsGenericTableEmpty
0x18001a1b9  test    al, al
0x18001a1bb  movzx   eax, dil
0x18001a1bf  setz    r14b
0x18001a1c3  and     byte ptr [rbx+2E1h], 0FDh
0x18001a1ca  add     al, al
0x18001a1cc  or      [rbx+2E1h], al
0x18001a1d2  test    dil, dil
0x18001a1d5  jnz     loc_18001A26A
0x18001a1db  test    bpl, 2
0x18001a1df  jnz     short loc_18001A216
0x18001a1e1  lea     rcx, [r15+1A8h]; Table
0x18001a1e8  call    cs:__imp_RtlIsGenericTableEmpty
0x18001a1ee  test    al, al
0x18001a1f0  setz    dil
0x18001a1f4  cmp     r14b, dil
0x18001a1f7  jnz     loc_18001A295
0x18001a1fd  add     rsp, 28h
0x18001a201  pop     r15
0x18001a203  pop     r14
0x18001a205  pop     rdi
0x18001a206  pop     rsi
0x18001a207  pop     rbp
0x18001a208  pop     rbx
0x18001a209  retn
0x18001a20a  cmp     qword ptr [rdx+20h], 0
0x18001a20f  jz      short loc_18001A1A9
0x18001a211  mov     dil, 1
0x18001a214  jmp     short loc_18001A1AC
0x18001a216  test    dil, dil
0x18001a219  jnz     short loc_18001A1E1
0x18001a21b  lea     rdx, [rsp+58h+Buffer]; Buffer
0x18001a220  mov     [rsp+58h+Buffer], rbx
0x18001a225  lea     rcx, [r15+1A8h]; Table
0x18001a22c  call    cs:__imp_RtlLookupElementGenericTable
0x18001a232  test    rax, rax
0x18001a235  jz      short loc_18001A1E1
0x18001a237  mov     rax, [rax]
0x18001a23a  lea     rdx, [rsp+58h+Buffer]; Buffer
0x18001a23f  lea     rcx, [r15+1A8h]; Table
0x18001a246  mov     [rsp+58h+Buffer], rax
0x18001a24b  call    cs:__imp_RtlDeleteElementGenericTable
0x18001a251  test    al, al
0x18001a253  jnz     short loc_18001A1E1
0x18001a255  xor     edx, edx; pContextRecord
0x18001a257  xor     ecx, ecx; pExceptionRecord
0x18001a259  mov     r8d, 1; dwFlags
0x18001a25f  call    cs:__imp_RaiseFailFastException
0x18001a265  jmp     loc_18001A1E1
0x18001a26a  test    bpl, 2
0x18001a26e  jnz     short loc_18001A216
0x18001a270  xor     r9d, r9d; NewElement
0x18001a273  mov     [rsp+58h+Buffer], rbx
0x18001a278  mov     r8d, 8; BufferSize
0x18001a27e  lea     rdx, [rsp+58h+Buffer]; Buffer
0x18001a283  lea     rcx, [r15+1A8h]; Table
0x18001a28a  call    cs:__imp_RtlInsertElementGenericTable
0x18001a290  jmp     loc_18001A1E1
0x18001a295  mov     rdx, [rbx+88h]; unsigned __int64
0x18001a29c  mov     rcx, r15; this
0x18001a29f  call    ?GetWindowListForDesktop@CWindowList@@QEAAPEAU_LIST_ENTRY@@_K@Z; CWindowList::GetWindowListForDesktop(unsigned __int64)
0x18001a2a4  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18001a2ab  mov     rsi, rax
0x18001a2ae  mov     [rcx+15h], dil
0x18001a2b2  mov     rbx, [rax]
0x18001a2b5  cmp     rbx, rax
0x18001a2b8  jz      loc_18001A1FD
0x18001a2be  xchg    ax, ax
0x18001a2c0  test    byte ptr [rbx+2E1h], 8
0x18001a2c7  jnz     short loc_18001A2D6
0x18001a2c9  mov     rbx, [rbx]
0x18001a2cc  cmp     rbx, rsi
0x18001a2cf  jnz     short loc_18001A2C0
0x18001a2d1  jmp     loc_18001A1FD
0x18001a2d6  mov     rcx, rbx; this
0x18001a2d9  call    ?OnColorizationUpdated@CWindowData@@QEAAXXZ; CWindowData::OnColorizationUpdated(void)
0x18001a2de  mov     rcx, [rbx+28h]; hWnd
0x18001a2e2  xor     r9d, r9d; lParam
0x18001a2e5  movzx   r8d, dil; wParam
0x18001a2e9  mov     edx, 321h; Msg
0x18001a2ee  call    cs:__imp_PostMessageW
0x18001a2f4  jmp     short loc_18001A2C9
```
