# TLoad64BitDllsMgr::ReleaseMonitorActivationContext(void *,void *,unsigned __int64,int)

- ea: `0x140007d54`
- end: `0x140007da4`
- name: `?ReleaseMonitorActivationContext@TLoad64BitDllsMgr@@IEBAXPEAX0_KH@Z`
- size: `80`
- prototype: `void(TLoad64BitDllsMgr *__hidden this, void *, void *, unsigned __int64, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400066c0`
- `0x1400067b0`
- `0x1400068d0`
- `0x140007548`

## callees

- `0x140007d54`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140007d6c`
- `KERNEL32!FreeLibrary` at `0x140007d6c`
- `KERNEL32!DeactivateActCtx` at `0x140007d7e`
- `KERNEL32!DeactivateActCtx` at `0x140007d7e`
- `KERNEL32!ReleaseActCtx` at `0x140007d93`
- `KERNEL32!ReleaseActCtx` at `0x140007d93`

## pseudocode

```c
void __fastcall TLoad64BitDllsMgr::ReleaseMonitorActivationContext(
        TLoad64BitDllsMgr *this,
        HMODULE a2,
        void *a3,
        ULONG_PTR a4,
        int a5)
{
  if ( a2 )
    FreeLibrary(a2);
  if ( a5 )
    DeactivateActCtx(0, a4);
  if ( (((unsigned __int64)a3 + 3) & 0xFFFFFFFFFFFFFFFDuLL) != 0 )
    ReleaseActCtx(a3);
}

```

## disassembly

```asm
0x140007d54  mov     [rsp+arg_0], rbx
0x140007d59  push    rdi
0x140007d5a  sub     rsp, 20h
0x140007d5e  mov     rdi, r9
0x140007d61  mov     rbx, r8
0x140007d64  test    rdx, rdx
0x140007d67  jz      short loc_140007D72
0x140007d69  mov     rcx, rdx; hLibModule
0x140007d6c  call    cs:__imp_FreeLibrary
0x140007d72  cmp     [rsp+28h+arg_20], 0
0x140007d77  jz      short loc_140007D84
0x140007d79  mov     rdx, rdi; ulCookie
0x140007d7c  xor     ecx, ecx; dwFlags
0x140007d7e  call    cs:__imp_DeactivateActCtx
0x140007d84  lea     rax, [rbx+3]
0x140007d88  test    rax, 0FFFFFFFFFFFFFFFDh
0x140007d8e  jz      short loc_140007D99
0x140007d90  mov     rcx, rbx; hActCtx
0x140007d93  call    cs:__imp_ReleaseActCtx
0x140007d99  mov     rbx, [rsp+28h+arg_0]
0x140007d9e  add     rsp, 20h
0x140007da2  pop     rdi
0x140007da3  retn
```
