# SdpDebugTrace(ulong,ushort const *,int,long)

- ea: `0x140005964`
- end: `0x140005a48`
- name: `?SdpDebugTrace@@YAXKPEBGHJ@Z`
- size: `228`
- prototype: `void __fastcall(__int64, const char *, unsigned int, int)`
- caller_count: `18`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140001ee4`
- `0x140002238`
- `0x140002490`
- `0x140002750`
- `0x1400027a4`
- `0x1400028e0`
- `0x140002a00`
- `0x140002af0`
- `0x140002c40`
- `0x140002d70`
- `0x1400055d8`
- `0x1400057b8`
- `0x140005a50`
- `0x140005ca4`
- `0x140005d7c`
- `0x140005eb8`
- `0x140005fec`
- `0x140006050`

## callees

- `0x1400058c0`
- `0x140005964`
- `0x1400075f0`
- `0x140007770`

## pseudocode

```c
void __fastcall SdpDebugTrace(__int64 a1, const char *a2, unsigned int a3, int a4)
{
  __int64 v7; // rax
  int v8; // ecx
  const char *v9; // rax
  PEVENT_DATA_DESCRIPTOR v10; // [rsp+20h] [rbp-29h]
  unsigned int v11; // [rsp+30h] [rbp-19h] BYREF
  int v12; // [rsp+38h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v13; // [rsp+40h] [rbp-9h] BYREF
  const char *v14; // [rsp+50h] [rbp+7h]
  int v15; // [rsp+58h] [rbp+Fh]
  int v16; // [rsp+5Ch] [rbp+13h]
  int *v17; // [rsp+60h] [rbp+17h]
  __int64 v18; // [rsp+68h] [rbp+1Fh]
  int *v19; // [rsp+70h] [rbp+27h]
  __int64 v20; // [rsp+78h] [rbp+2Fh]

  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 8) != 0 )
  {
    v11 = a3;
    v12 = a4;
    if ( a2 )
    {
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)&a2[2 * v7] );
      v8 = 2 * v7 + 2;
    }
    else
    {
      v8 = 10;
    }
    v15 = v8;
    v16 = 0;
    v9 = a2;
    v18 = 4;
    if ( !a2 )
      v9 = L"NULL";
    v20 = 4;
    v14 = v9;
    v17 = (int *)&v11;
    v19 = &v12;
    McGenEventWrite_EventWriteTransfer(v8, (int)L"NULL", 0, a4, &v13);
  }
  LODWORD(v10) = a4;
  SdpDebugPrint(1u, "SDIAG: %ws:%d - hr = 0x%08X\n", a2, a3, v10);
}

```

## disassembly

```asm
0x140005964  mov     [rsp-8+arg_0], rbx
0x140005969  push    rbp
0x14000596a  push    rsi
0x14000596b  push    rdi
0x14000596c  lea     rbp, [rsp-47h]
0x140005971  sub     rsp, 90h
0x140005978  mov     rax, cs:__security_cookie
0x14000597f  xor     rax, rsp
0x140005982  mov     [rbp+57h+var_20], rax
0x140005986  test    cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 8
0x14000598d  mov     esi, r9d
0x140005990  mov     edi, r8d
0x140005993  mov     rbx, rdx
0x140005996  jz      short loc_140005A0E
0x140005998  mov     [rbp+57h+var_70], r8d
0x14000599c  xor     r8d, r8d; int
0x14000599f  mov     [rbp+57h+var_68], r9d
0x1400059a3  test    rdx, rdx
0x1400059a6  jz      short loc_1400059BF
0x1400059a8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400059ac  inc     rax
0x1400059af  cmp     [rdx+rax*2], r8w
0x1400059b4  jnz     short loc_1400059AC
0x1400059b6  lea     ecx, ds:2[rax*2]
0x1400059bd  jmp     short loc_1400059C4
0x1400059bf  mov     ecx, 0Ah; int
0x1400059c4  test    rbx, rbx
0x1400059c7  mov     [rbp+57h+var_48], ecx
0x1400059ca  lea     rdx, aNull; "NULL"
0x1400059d1  mov     [rbp+57h+var_44], r8d
0x1400059d5  mov     rax, rbx
0x1400059d8  mov     [rbp+57h+var_38], 4
0x1400059e0  cmovz   rax, rdx
0x1400059e4  mov     [rbp+57h+var_28], 4
0x1400059ec  mov     [rbp+57h+var_50], rax
0x1400059f0  lea     rax, [rbp+57h+var_70]
0x1400059f4  mov     [rbp+57h+var_40], rax
0x1400059f8  lea     rax, [rbp+57h+var_68]
0x1400059fc  mov     [rbp+57h+var_30], rax
0x140005a00  lea     rax, [rbp+57h+var_60]
0x140005a04  mov     [rsp+0A0h+var_80], rax; PEVENT_DATA_DESCRIPTOR
0x140005a09  call    McGenEventWrite_EventWriteTransfer
0x140005a0e  mov     r9d, edi
0x140005a11  mov     dword ptr [rsp+0A0h+var_80], esi
0x140005a15  mov     r8, rbx
0x140005a18  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x140005a1f  mov     ecx, 1; Level
0x140005a24  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x140005a29  mov     rcx, [rbp+57h+var_20]
0x140005a2d  xor     rcx, rsp; StackCookie
0x140005a30  call    __security_check_cookie
0x140005a35  mov     rbx, [rsp+0A0h+arg_0]
0x140005a3d  add     rsp, 90h
0x140005a44  pop     rdi
0x140005a45  pop     rsi
0x140005a46  pop     rbp
0x140005a47  retn
```
