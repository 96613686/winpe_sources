# SdbpGetSystemSdbFilePath

- ea: `0x140013638`
- end: `0x14001372f`
- name: `SdbpGetSystemSdbFilePath`
- size: `247`
- prototype: `__int64 __fastcall(_WORD *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140012be0`

## callees

- `0x14001008c`
- `0x140013638`
- `0x14002f010`

## string_xrefs

- `0x140013682`: `SdbpGetSystemSdbFilePath`
- `0x1400136b3`: `SdbpGetSystemSdbFilePath`
- `0x140013704`: `SdbpGetSystemSdbFilePath`
- `0x1400136a6`: `SdbFileDetails missing function pointer for path.`
- `0x1400136f5`: `GetPathFunction (for SdbFileType %d, IsLtRs3: %d) failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpGetSystemSdbFilePath(_WORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v5; // rdx
  __int64 *v6; // r8
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(_WORD *, __int64, __int64, _QWORD); // r10
  __int64 v9; // rax
  int v10; // eax

  *a1 = 0;
  v5 = 1;
  while ( 1 )
  {
    v6 = &qword_140030AB0[4 * v5];
    if ( *(_DWORD *)v6 == 10 )
      break;
    if ( (unsigned __int64)++v5 >= 0xD )
      goto LABEL_6;
  }
  if ( !v6 )
  {
LABEL_6:
    AslLogCallPrintf(1, "SdbpGetSystemSdbFilePath", 1373, "SdbFileDetails missing array item for SdbFileType: %d", 10);
    return (unsigned int)-1073741275;
  }
  v8 = (__int64 (__fastcall *)(_WORD *, __int64, __int64, _QWORD))v6[2];
  if ( v8 )
  {
    v9 = a5;
    if ( !a5 )
      v9 = v6[1];
    v10 = v8(a1, 260, v9, 0);
    v7 = v10;
    if ( v10 >= 0 )
      return 0;
    else
      AslLogCallPrintf(
        1,
        "SdbpGetSystemSdbFilePath",
        1397,
        "GetPathFunction (for SdbFileType %d, IsLtRs3: %d) failed [%x]",
        10,
        0,
        v10);
  }
  else
  {
    AslLogCallPrintf(1, "SdbpGetSystemSdbFilePath", 1387, "SdbFileDetails missing function pointer for path.");
    return (unsigned int)-1073741595;
  }
  return v7;
}

```

## disassembly

```asm
0x140013638  push    rbx
0x14001363a  sub     rsp, 40h
0x14001363e  xor     eax, eax
0x140013640  mov     [rcx], ax
0x140013643  lea     edx, [rax+1]
0x140013646  mov     rax, rdx
0x140013649  lea     r8, qword_140030AB0
0x140013650  shl     rax, 5
0x140013654  add     r8, rax
0x140013657  cmp     dword ptr [r8], 0Ah
0x14001365b  jz      short loc_140013668
0x14001365d  inc     rdx
0x140013660  cmp     rdx, 0Dh
0x140013664  jb      short loc_140013646
0x140013666  jmp     short loc_14001366D
0x140013668  test    r8, r8
0x14001366b  jnz     short loc_14001369D
0x14001366d  lea     r9, aSdbfiledetails; "SdbFileDetails missing array item for S"...
0x140013674  mov     [rsp+48h+var_28], 0Ah
0x14001367c  mov     r8d, 55Dh
0x140013682  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePath"
0x140013689  mov     ecx, 1
0x14001368e  call    AslLogCallPrintf
0x140013693  mov     ebx, 0C0000225h
0x140013698  jmp     loc_140013727
0x14001369d  mov     r10, [r8+10h]
0x1400136a1  test    r10, r10
0x1400136a4  jnz     short loc_1400136CA
0x1400136a6  lea     r9, aSdbfiledetails_0; "SdbFileDetails missing function pointer"...
0x1400136ad  mov     r8d, 56Bh
0x1400136b3  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePath"
0x1400136ba  lea     ecx, [r10+1]
0x1400136be  call    AslLogCallPrintf
0x1400136c3  mov     ebx, 0C00000E5h
0x1400136c8  jmp     short loc_140013727
0x1400136ca  mov     rax, [rsp+48h+arg_20]
0x1400136cf  test    rax, rax
0x1400136d2  jnz     short loc_1400136D8
0x1400136d4  mov     rax, [r8+8]
0x1400136d8  mov     r8, rax
0x1400136db  xor     r9d, r9d
0x1400136de  mov     rax, r10
0x1400136e1  mov     edx, 104h
0x1400136e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400136eb  mov     ebx, eax
0x1400136ed  test    eax, eax
0x1400136ef  jns     short loc_140013725
0x1400136f1  mov     [rsp+48h+var_18], eax
0x1400136f5  lea     r9, aGetpathfunctio; "GetPathFunction (for SdbFileType %d, Is"...
0x1400136fc  mov     [rsp+48h+var_20], 0
0x140013704  lea     rdx, aSdbpgetsystems_0; "SdbpGetSystemSdbFilePath"
0x14001370b  mov     r8d, 575h
0x140013711  mov     [rsp+48h+var_28], 0Ah
0x140013719  mov     ecx, 1
0x14001371e  call    AslLogCallPrintf
0x140013723  jmp     short loc_140013727
0x140013725  xor     ebx, ebx
0x140013727  mov     eax, ebx
0x140013729  add     rsp, 40h
0x14001372d  pop     rbx
0x14001372e  retn
```
