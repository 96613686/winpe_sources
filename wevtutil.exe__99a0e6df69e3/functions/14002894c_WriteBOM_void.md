# WriteBOM(void *)

- ea: `0x14002894c`
- end: `0x1400289fc`
- name: `?WriteBOM@@YAXPEAX@Z`
- size: `176`
- prototype: `void __fastcall(void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140008db0`
- `0x14001b75c`

## callees

- `0x140022cec`
- `0x14002894c`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028986`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140028986`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002897c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14002897c`

## pseudocode

```c
void __fastcall WriteBOM(void *a1)
{
  DWORD LastError; // ebx
  const char *v2; // r8
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF
  __int16 v4; // [rsp+78h] [rbp+10h] BYREF
  DWORD v5; // [rsp+80h] [rbp+18h] BYREF

  v5 = 0;
  v4 = -257;
  if ( !WriteFile(a1, &v4, 2u, &v5, 0) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, v2, 126);
    throw (EvtException *)pExceptionObject;
  }
}

```

## disassembly

```asm
0x14002894c  mov     r11, rsp
0x14002894f  push    rbx
0x140028950  sub     rsp, 60h
0x140028954  mov     eax, 0FEFFh
0x140028959  mov     dword ptr [r11+18h], 0
0x140028961  lea     r9, [r11+18h]; lpNumberOfBytesWritten
0x140028965  mov     [rsp+68h+arg_8], ax
0x14002896a  mov     r8d, 2; nNumberOfBytesToWrite
0x140028970  mov     qword ptr [r11-48h], 0
0x140028978  lea     rdx, [r11+10h]; lpBuffer
0x14002897c  call    cs:__imp_WriteFile
0x140028982  test    eax, eax
0x140028984  jnz     short loc_1400289F6
0x140028986  call    cs:__imp_GetLastError
0x14002898c  mov     ebx, eax
0x14002898e  mov     eax, 507h
0x140028993  test    ebx, ebx
0x140028995  cmovz   ebx, eax
0x140028998  mov     rcx, cs:WPP_GLOBAL_Control
0x14002899f  lea     rax, WPP_GLOBAL_Control
0x1400289a6  cmp     rcx, rax
0x1400289a9  jz      short loc_1400289D2
0x1400289ab  test    dword ptr [rcx+1Ch], 400000h
0x1400289b2  jz      short loc_1400289D2
0x1400289b4  cmp     byte ptr [rcx+19h], 2
0x1400289b8  jb      short loc_1400289D2
0x1400289ba  mov     rcx, [rcx+10h]
0x1400289be  lea     r8, WPP_c61a5d7454d73d433a227fa9485a0fb8_Traceguids
0x1400289c5  mov     edx, 0Bh
0x1400289ca  mov     r9d, ebx
0x1400289cd  call    WPP_SF_d
0x1400289d2  mov     r9d, 7Eh ; '~'; int
0x1400289d8  lea     rcx, [rsp+68h+pExceptionObject]; this
0x1400289dd  mov     edx, ebx; unsigned int
0x1400289df  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400289e4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400289eb  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x1400289f0  call    _CxxThrowException_0
0x1400289f6  add     rsp, 60h
0x1400289fa  pop     rbx
0x1400289fb  retn
```
