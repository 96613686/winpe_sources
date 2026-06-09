# _DeleteDirectoryTraverseCallback

- ea: `0x18001dfe0`
- end: `0x18001e090`
- name: `_DeleteDirectoryTraverseCallback`
- size: `176`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001d4dc`

## callees

- `0x18000ea0c`
- `0x18001586c`
- `0x180015974`
- `0x18001d154`
- `0x18001dd98`
- `0x18001dfe0`

## string_xrefs

- `0x18001e027`: `_DeleteDirectoryTraverseCallback`

## pseudocode

```c
__int64 __fastcall DeleteDirectoryTraverseCallback(__int64 a1, const WCHAR *a2, int a3)
{
  int v5; // ebx
  bool v6; // sf
  __int16 v7; // ax
  int v9; // [rsp+20h] [rbp-48h] BYREF
  __int16 v10; // [rsp+24h] [rbp-44h]
  __int16 v11; // [rsp+26h] [rbp-42h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v9, "_DeleteDirectoryTraverseCallback", 0x7B6u, 1u);
  if ( a3 )
  {
    v5 = DeleteDirectory(a2);
    v9 = v5;
    v6 = v5 < 0;
    v7 = 1980;
  }
  else
  {
    v5 = SxDeleteFile(a2);
    v9 = v5;
    v6 = v5 < 0;
    v7 = 1984;
  }
  if ( v6 )
    v11 = v7;
  else
    v10 = v7;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v9);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001dfe0  mov     [rsp+arg_0], rbx
0x18001dfe5  push    rdi
0x18001dfe6  sub     rsp, 60h
0x18001dfea  mov     edi, r8d
0x18001dfed  mov     rbx, rdx
0x18001dff0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dff7  lea     rax, WPP_GLOBAL_Control
0x18001dffe  cmp     rcx, rax
0x18001e001  jz      short loc_18001E021
0x18001e003  test    dword ptr [rcx+1Ch], 20000000h
0x18001e00a  jz      short loc_18001E021
0x18001e00c  mov     rcx, [rcx+10h]
0x18001e010  lea     r8, WPP_b1bfb7512cf23544267720d0f520c3da_Traceguids
0x18001e017  mov     edx, 36h ; '6'
0x18001e01c  call    WPP_SF_
0x18001e021  mov     r9d, 1; unsigned __int16
0x18001e027  lea     rdx, aDeletedirector; "_DeleteDirectoryTraverseCallback"
0x18001e02e  mov     r8d, 7B6h; unsigned __int16
0x18001e034  lea     rcx, [rsp+68h+var_48]; this
0x18001e039  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e03e  mov     rcx, rbx; lpFileName
0x18001e041  test    edi, edi
0x18001e043  jz      short loc_18001E060
0x18001e045  call    _DeleteDirectory
0x18001e04a  mov     ebx, eax
0x18001e04c  mov     [rsp+68h+var_48], eax
0x18001e050  test    eax, eax
0x18001e052  mov     eax, 7BCh
0x18001e057  jns     short loc_18001E074
0x18001e059  mov     [rsp+68h+var_42], ax
0x18001e05e  jmp     short loc_18001E079
0x18001e060  call    ?SxDeleteFile@@YAJPEBG@Z; SxDeleteFile(ushort const *)
0x18001e065  mov     ebx, eax
0x18001e067  mov     [rsp+68h+var_48], eax
0x18001e06b  test    eax, eax
0x18001e06d  mov     eax, 7C0h
0x18001e072  jmp     short loc_18001E057
0x18001e074  mov     [rsp+68h+var_44], ax
0x18001e079  lea     rcx, [rsp+68h+var_48]; this
0x18001e07e  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e083  mov     eax, ebx
0x18001e085  mov     rbx, [rsp+68h+arg_0]
0x18001e08a  add     rsp, 60h
0x18001e08e  pop     rdi
0x18001e08f  retn
```
