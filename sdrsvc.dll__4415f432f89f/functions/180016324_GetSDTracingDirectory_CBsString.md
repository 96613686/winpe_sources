# GetSDTracingDirectory(CBsString *)

- ea: `0x180016324`
- end: `0x1800163f7`
- name: `?GetSDTracingDirectory@@YAJPEAVCBsString@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(struct CBsString *this)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016400`
- `0x180016520`

## callees

- `0x18001586c`
- `0x180015974`
- `0x180016324`
- `0x18001f720`
- `0x18001ffb4`

## string_xrefs

- `0x180016341`: `GetSDTracingDirectory`

## pseudocode

```c
__int64 __fastcall GetSDTracingDirectory(struct CBsString *this)
{
  __int16 v2; // ax
  int v3; // ebx
  const unsigned __int16 *v4; // r9
  bool v5; // zf
  int v7; // [rsp+60h] [rbp+17h] BYREF
  __int16 v8; // [rsp+64h] [rbp+1Bh]
  __int16 v9; // [rsp+66h] [rbp+1Dh]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "GetSDTracingDirectory", 54, 1);
  v2 = 56;
  if ( this )
  {
    v7 = 0;
    v8 = 56;
    v3 = CBsString::ExpandEnvironmentStringsW(this, L"%SystemRoot%\\Logs");
    v7 = v3;
    v2 = 58;
    if ( v3 >= 0 )
    {
      v5 = *((_DWORD *)this + 2) == 0;
      v8 = 58;
      if ( v5 )
      {
        v3 = -2147020579;
        v7 = -2147020579;
      }
      else
      {
        v7 = CBsString::_CombinePathImpl(this, L"WindowsBackup", 0, v4);
        v3 = v7;
        if ( v7 >= 0 )
        {
          v8 = 59;
          goto LABEL_10;
        }
      }
      v2 = 59;
    }
  }
  else
  {
    v3 = -2147024809;
    v7 = -2147024809;
  }
  v9 = v2;
LABEL_10:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180016324  mov     [rsp-8+arg_0], rbx
0x180016329  mov     [rsp-8+arg_8], rdi
0x18001632e  push    rbp
0x18001632f  lea     rbp, [rsp-57h]
0x180016334  sub     rsp, 0A0h
0x18001633b  mov     r9d, 1; unsigned __int16
0x180016341  lea     rdx, aGetsdtracingdi; "GetSDTracingDirectory"
0x180016348  mov     rdi, rcx
0x18001634b  lea     rcx, [rbp+57h+var_40]; this
0x18001634f  lea     r8d, [r9+35h]; unsigned __int16
0x180016353  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180016358  mov     eax, 38h ; '8'
0x18001635d  test    rdi, rdi
0x180016360  jnz     short loc_180016370
0x180016362  mov     ebx, 80070057h
0x180016367  mov     [rbp+57h+var_40], ebx
0x18001636a  mov     [rbp+57h+var_3A], ax
0x18001636e  jmp     short loc_1800163D7
0x180016370  lea     rdx, Src; "%SystemRoot%\\Logs"
0x180016377  mov     [rbp+57h+var_40], 0
0x18001637e  mov     rcx, rdi; this
0x180016381  mov     [rbp+57h+var_3C], ax
0x180016385  call    ?ExpandEnvironmentStringsW@CBsString@@QEAAJPEBG@Z; CBsString::ExpandEnvironmentStringsW(ushort const *)
0x18001638a  mov     ebx, eax
0x18001638c  mov     [rbp+57h+var_40], eax
0x18001638f  test    eax, eax
0x180016391  mov     eax, 3Ah ; ':'
0x180016396  js      short loc_18001636A
0x180016398  cmp     dword ptr [rdi+8], 0
0x18001639c  mov     [rbp+57h+var_3C], ax
0x1800163a0  jnz     short loc_1800163AC
0x1800163a2  mov     ebx, 800710DDh
0x1800163a7  mov     [rbp+57h+var_40], ebx
0x1800163aa  jmp     short loc_1800163C7
0x1800163ac  xor     r8d, r8d; unsigned __int16 *
0x1800163af  lea     rdx, aWindowsbackup; "WindowsBackup"
0x1800163b6  mov     rcx, rdi; this
0x1800163b9  call    ?_CombinePathImpl@CBsString@@AEAAJPEBG000000000@Z; CBsString::_CombinePathImpl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800163be  mov     [rbp+57h+var_40], eax
0x1800163c1  mov     ebx, eax
0x1800163c3  test    eax, eax
0x1800163c5  jns     short loc_1800163CE
0x1800163c7  mov     eax, 3Bh ; ';'
0x1800163cc  jmp     short loc_18001636A
0x1800163ce  mov     eax, 3Bh ; ';'
0x1800163d3  mov     [rbp+57h+var_3C], ax
0x1800163d7  lea     rcx, [rbp+57h+var_40]; this
0x1800163db  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x1800163e0  lea     r11, [rsp+0A0h+var_s0]
0x1800163e8  mov     eax, ebx
0x1800163ea  mov     rbx, [r11+10h]
0x1800163ee  mov     rdi, [r11+18h]
0x1800163f2  mov     rsp, r11
0x1800163f5  pop     rbp
0x1800163f6  retn
```
