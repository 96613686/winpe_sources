# PnPExceptionHandler

- ea: `0x180013d90`
- end: `0x180013df0`
- name: `PnPExceptionHandler`
- size: `96`
- prototype: `void __fastcall(NTSTATUS, __int64, int *)`
- caller_count: `11`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180008220`
- `0x180008bf0`
- `0x180009a20`
- `0x18000bc30`
- `0x1800121f0`
- `0x180013bdc`
- `0x180013c54`
- `0x1800144b0`
- `0x1800146d0`
- `0x1800148a0`
- `0x180015550`

## callees

- `0x180013d90`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180013da1`
- `ntdll!RtlNtStatusToDosError` at `0x180013da1`

## pseudocode

```c
void __fastcall PnPExceptionHandler(NTSTATUS a1, __int64 a2, int *a3)
{
  ULONG v4; // eax
  int v5; // ecx
  ULONG v6; // eax
  ULONG v7; // eax
  ULONG v8; // eax
  ULONG v9; // eax

  if ( a1 == -1073741819 || (v4 = RtlNtStatusToDosError(a1), v4 == 317) )
  {
LABEL_8:
    v5 = 19;
    goto LABEL_9;
  }
  v5 = 2;
  v6 = v4 - 2;
  if ( v6 && (v7 = v6 - 1) != 0 )
  {
    v8 = v7 - 2;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        if ( v9 == 2 )
          goto LABEL_9;
        goto LABEL_8;
      }
      v5 = 28;
    }
    else
    {
      v5 = 51;
    }
  }
  else
  {
    v5 = 37;
  }
LABEL_9:
  if ( a3 )
    *a3 = v5;
}

```

## disassembly

```asm
0x180013d90  push    rbx
0x180013d92  sub     rsp, 20h
0x180013d96  mov     rbx, r8
0x180013d99  cmp     ecx, 0C0000005h
0x180013d9f  jz      short loc_180013DC9
0x180013da1  call    cs:__imp_RtlNtStatusToDosError
0x180013da7  cmp     eax, 13Dh
0x180013dac  jz      short loc_180013DC9
0x180013dae  mov     ecx, 2
0x180013db3  sub     eax, ecx
0x180013db5  jz      short loc_180013DE9
0x180013db7  sub     eax, 1
0x180013dba  jz      short loc_180013DE9
0x180013dbc  sub     eax, ecx
0x180013dbe  jz      short loc_180013DE2
0x180013dc0  sub     eax, 1
0x180013dc3  jz      short loc_180013DDB
0x180013dc5  cmp     eax, ecx
0x180013dc7  jz      short loc_180013DCE
0x180013dc9  mov     ecx, 13h
0x180013dce  test    rbx, rbx
0x180013dd1  jz      short loc_180013DD5
0x180013dd3  mov     [rbx], ecx
0x180013dd5  add     rsp, 20h
0x180013dd9  pop     rbx
0x180013dda  retn
0x180013ddb  mov     ecx, 1Ch
0x180013de0  jmp     short loc_180013DCE
0x180013de2  mov     ecx, 33h ; '3'
0x180013de7  jmp     short loc_180013DCE
0x180013de9  mov     ecx, 25h ; '%'
0x180013dee  jmp     short loc_180013DCE
```
