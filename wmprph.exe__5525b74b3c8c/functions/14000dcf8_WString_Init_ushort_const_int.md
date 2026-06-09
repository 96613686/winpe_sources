# WString::Init(ushort const *,int)

- ea: `0x14000dcf8`
- end: `0x14000dd92`
- name: `?Init@WString@@QEAAJPEBGH@Z`
- size: `154`
- prototype: `__int64 __fastcall(WString *__hidden this, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140005910`
- `0x140005c60`
- `0x14000e078`

## callees

- `0x140001d02`
- `0x14000d978`
- `0x14000dcf8`
- `0x14000dd98`
- `0x14000de4c`
- `0x14000e1ec`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x14000dd18`
- `KERNEL32!lstrlenW` at `0x14000dd18`

## pseudocode

```c
__int64 __fastcall WString::Init(unsigned __int16 **this, WCHAR *a2)
{
  int v5; // eax
  rsize_t v6; // rbp
  wchar_t *v7; // rax
  unsigned __int16 *v8; // rsi
  rsize_t v9; // rdx

  if ( !a2 )
  {
    WString::DeleteString(this);
    return 0;
  }
  v5 = lstrlenW(a2);
  v6 = v5;
  if ( v5 + 1 >= 0 )
  {
    if ( (*((_BYTE *)this + 12) & 0x20) != 0 )
    {
      StringCchCopyNW(*this, *((int *)this + 2), a2, v5);
      return 0;
    }
    v7 = WString::InternalAllocate((WString *)this, v5 + 1);
    v8 = v7;
    if ( v7 )
    {
      v9 = v6 + 1;
      if ( (*((_BYTE *)this + 12) & 4) != 0 )
      {
        o_wmemcpy_s_0(v7, v9, a2, v6);
        v8[v6] = 0;
      }
      else
      {
        StringCchCopyNW(v7, v9, a2, v6);
      }
      WString::InternalAttach((WString *)this, v8);
      return 0;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x14000dcf8  push    rbx
0x14000dcfa  push    rbp
0x14000dcfb  push    rsi
0x14000dcfc  push    rdi
0x14000dcfd  sub     rsp, 28h
0x14000dd01  mov     rdi, rdx
0x14000dd04  mov     rbx, rcx
0x14000dd07  test    rdx, rdx
0x14000dd0a  jnz     short loc_14000DD15
0x14000dd0c  call    ?DeleteString@WString@@QEAAXXZ; WString::DeleteString(void)
0x14000dd11  xor     eax, eax
0x14000dd13  jmp     short loc_14000DD89
0x14000dd15  mov     rcx, rdi; lpString
0x14000dd18  call    cs:__imp_lstrlenW
0x14000dd1e  movsxd  rbp, eax
0x14000dd21  lea     edx, [rbp+1]; int
0x14000dd24  test    edx, edx
0x14000dd26  js      short loc_14000DD84
0x14000dd28  test    byte ptr [rbx+0Ch], 20h
0x14000dd2c  jz      short loc_14000DD42
0x14000dd2e  movsxd  rdx, dword ptr [rbx+8]; unsigned __int64
0x14000dd32  mov     r9, rbp; unsigned __int64
0x14000dd35  mov     rcx, [rbx]; unsigned __int16 *
0x14000dd38  mov     r8, rdi; unsigned __int16 *
0x14000dd3b  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000dd40  jmp     short loc_14000DD11
0x14000dd42  mov     rcx, rbx; this
0x14000dd45  call    ?InternalAllocate@WString@@IEBAPEAGH@Z; WString::InternalAllocate(int)
0x14000dd4a  mov     rsi, rax
0x14000dd4d  test    rax, rax
0x14000dd50  jz      short loc_14000DD84
0x14000dd52  test    byte ptr [rbx+0Ch], 4
0x14000dd56  lea     rdx, [rbp+1]; unsigned __int64
0x14000dd5a  mov     r9, rbp; unsigned __int64
0x14000dd5d  mov     r8, rdi; unsigned __int16 *
0x14000dd60  mov     rcx, rax; unsigned __int16 *
0x14000dd63  jz      short loc_14000DD72
0x14000dd65  call    _o_wmemcpy_s_0
0x14000dd6a  xor     eax, eax
0x14000dd6c  mov     [rsi+rbp*2], ax
0x14000dd70  jmp     short loc_14000DD77
0x14000dd72  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x14000dd77  mov     rdx, rsi; unsigned __int16 *
0x14000dd7a  mov     rcx, rbx; this
0x14000dd7d  call    ?InternalAttach@WString@@IEAAXPEAG@Z; WString::InternalAttach(ushort *)
0x14000dd82  jmp     short loc_14000DD11
0x14000dd84  mov     eax, 8007000Eh
0x14000dd89  add     rsp, 28h
0x14000dd8d  pop     rdi
0x14000dd8e  pop     rsi
0x14000dd8f  pop     rbp
0x14000dd90  pop     rbx
0x14000dd91  retn
```
