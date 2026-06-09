# SxRegWriteULONGLONG(HKEY__ *,ushort const *,unsigned __int64)

- ea: `0x140005c10`
- end: `0x140005cc7`
- name: `?SxRegWriteULONGLONG@@YAJPEAUHKEY__@@PEBG_K@Z`
- size: `183`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1400020c4`

## callees

- `0x140005c10`
- `0x14000e324`
- `0x14000e41c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140005c8e`
- `ADVAPI32!RegSetValueExW` at `0x140005c8e`

## string_xrefs

- `0x140005c66`: `LastMainenanceTaskRunTimeStamp`
- `0x140005c1d`: `SxRegWriteULONGLONG`

## pseudocode

```c
__int64 __fastcall SxRegWriteULONGLONG(HKEY hKey, const unsigned __int16 *a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  signed int v6; // ebx
  __int16 v7; // ax
  LSTATUS v8; // eax
  int v10; // [rsp+30h] [rbp-48h] BYREF
  __int16 v11; // [rsp+34h] [rbp-44h]
  __int16 v12; // [rsp+36h] [rbp-42h]
  __int64 Data; // [rsp+90h] [rbp+18h] BYREF

  Data = a3;
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v10, "SxRegWriteULONGLONG", 458, 2);
  if ( hKey )
  {
    v11 = 461;
    v10 = 0;
    v8 = RegSetValueExW(hKey, L"LastMainenanceTaskRunTimeStamp", 0, 0xBu, (const BYTE *)&Data, 8u);
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    v10 = v6;
    v7 = 463;
    if ( v6 >= 0 )
    {
      v11 = 463;
      goto LABEL_8;
    }
  }
  else
  {
    v6 = -2147024809;
    v7 = 460;
    v10 = -2147024809;
  }
  v12 = v7;
LABEL_8:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v10, v4, v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140005c10  mov     [rsp+Data], r8
0x140005c15  push    rbx
0x140005c16  sub     rsp, 70h
0x140005c1a  mov     rbx, rcx
0x140005c1d  lea     rdx, aSxregwriteulon; "SxRegWriteULONGLONG"
0x140005c24  lea     rcx, [rsp+78h+var_48]; this
0x140005c29  mov     r9d, 2; unsigned __int16
0x140005c2f  mov     r8d, 1CAh; unsigned __int16
0x140005c35  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x140005c3a  test    rbx, rbx
0x140005c3d  jnz     short loc_140005C54
0x140005c3f  mov     ebx, 80070057h
0x140005c44  mov     eax, 1CCh
0x140005c49  mov     [rsp+78h+var_48], ebx
0x140005c4d  mov     [rsp+78h+var_42], ax
0x140005c52  jmp     short loc_140005CB5
0x140005c54  mov     eax, 1CDh
0x140005c59  mov     [rsp+78h+cbData], 8; cbData
0x140005c61  mov     [rsp+78h+var_44], ax
0x140005c66  lea     rdx, c_wszSRLastMainenanceTaskRun; "LastMainenanceTaskRunTimeStamp"
0x140005c6d  lea     rax, [rsp+78h+Data]
0x140005c75  mov     [rsp+78h+var_48], 0
0x140005c7d  mov     r9d, 0Bh; dwType
0x140005c83  mov     [rsp+78h+lpData], rax; lpData
0x140005c88  xor     r8d, r8d; Reserved
0x140005c8b  mov     rcx, rbx; hKey
0x140005c8e  call    cs:__imp_RegSetValueExW
0x140005c94  mov     ebx, eax
0x140005c96  test    eax, eax
0x140005c98  jle     short loc_140005CA3
0x140005c9a  movzx   ebx, ax
0x140005c9d  or      ebx, 80070000h
0x140005ca3  mov     [rsp+78h+var_48], ebx
0x140005ca7  mov     eax, 1CFh
0x140005cac  test    ebx, ebx
0x140005cae  js      short loc_140005C4D
0x140005cb0  mov     [rsp+78h+var_44], ax
0x140005cb5  lea     rcx, [rsp+78h+var_48]; this
0x140005cba  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x140005cbf  mov     eax, ebx
0x140005cc1  add     rsp, 70h
0x140005cc5  pop     rbx
0x140005cc6  retn
```
