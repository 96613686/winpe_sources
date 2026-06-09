# SdpDebugTrace(ulong,ushort const *,int,long)

- ea: `0x180026fa0`
- end: `0x180027084`
- name: `?SdpDebugTrace@@YAXKPEBGHJ@Z`
- size: `228`
- prototype: `void __fastcall(ULONG Level, const unsigned __int16 *, unsigned int, int)`
- caller_count: `254`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800020f8`
- `0x180002280`
- `0x180002338`
- `0x180002554`
- `0x1800025c8`
- `0x1800026a0`
- `0x180002798`
- `0x1800027f8`
- `0x1800028d0`
- `0x180002a30`
- `0x180002b34`
- `0x180002d20`
- `0x18000312c`
- `0x18000330c`
- `0x180003410`
- `0x1800034c4`
- `0x180003814`
- `0x1800038c4`
- `0x180003b2c`
- `0x180003e50`
- `0x1800040e8`
- `0x180004380`
- `0x180004518`
- `0x180004d58`
- `0x18000533c`
- `0x180005590`
- `0x18000571c`
- `0x180005ad0`
- `0x180005d60`
- `0x180005ffc`
- `0x18000615c`
- `0x180006620`
- `0x1800066f8`
- `0x18000680c`
- `0x18000698c`
- `0x180006a90`
- `0x180006ca0`
- `0x180007000`
- `0x180007184`
- `0x18000729c`
- `0x1800073a0`
- `0x180007528`
- `0x1800076a4`
- `0x1800077a0`
- `0x18000787c`
- `0x180007bc0`
- `0x180007f0c`
- `0x180008184`
- `0x18000a000`
- `0x18000a2f4`

## callees

- `0x1800130d0`
- `0x180026efc`
- `0x180026fa0`
- `0x1800298c0`

## pseudocode

```c
void __fastcall SdpDebugTrace(ULONG Level, const unsigned __int16 *a2, unsigned int a3, int a4)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  const wchar_t *v10; // rax
  __int64 v11; // [rsp+20h] [rbp-39h]
  unsigned int v12; // [rsp+30h] [rbp-29h] BYREF
  int v13; // [rsp+38h] [rbp-21h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-19h] BYREF
  const wchar_t *v15; // [rsp+50h] [rbp-9h]
  int v16; // [rsp+58h] [rbp-1h]
  int v17; // [rsp+5Ch] [rbp+3h]
  int *v18; // [rsp+60h] [rbp+7h]
  __int64 v19; // [rsp+68h] [rbp+Fh]
  int *v20; // [rsp+70h] [rbp+17h]
  __int64 v21; // [rsp+78h] [rbp+1Fh]

  if ( (Microsoft_Windows_Diagnosis_ScriptedEnableBits & 8) != 0 )
  {
    v12 = a3;
    v13 = a4;
    if ( a2 )
    {
      v8 = -1;
      do
        ++v8;
      while ( a2[v8] );
      v9 = (unsigned int)(2 * v8 + 2);
    }
    else
    {
      v9 = 10;
    }
    v16 = v9;
    v17 = 0;
    v19 = 4;
    v10 = a2;
    v21 = 4;
    if ( !a2 )
      v10 = L"NULL";
    v15 = v10;
    v18 = (int *)&v12;
    v20 = &v13;
    McGenEventWrite_EventWriteTransfer(v9, SCRIPTED_DIAGNOSTICS_EVENT_DEBUG, 0, 4, v14);
  }
  LODWORD(v11) = a4;
  SdpDebugPrint(Level, "SDIAG: %ws:%d - hr = 0x%08X\n", a2, a3, v11);
}

```

## disassembly

```asm
0x180026fa0  push    rbp
0x180026fa2  push    rbx
0x180026fa3  push    rsi
0x180026fa4  push    rdi
0x180026fa5  push    r14
0x180026fa7  lea     rbp, [rsp-37h]
0x180026fac  sub     rsp, 90h
0x180026fb3  mov     rax, cs:__security_cookie
0x180026fba  xor     rax, rsp
0x180026fbd  mov     [rbp+57h+var_30], rax
0x180026fc1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 8
0x180026fc8  mov     esi, r9d
0x180026fcb  mov     edi, r8d
0x180026fce  mov     rbx, rdx
0x180026fd1  mov     r14d, ecx
0x180026fd4  jz      short loc_180027051
0x180026fd6  mov     [rbp+57h+var_80], r8d
0x180026fda  xor     r8d, r8d
0x180026fdd  mov     [rbp+57h+var_78], r9d
0x180026fe1  test    rdx, rdx
0x180026fe4  jz      short loc_180026FFD
0x180026fe6  or      rax, 0FFFFFFFFFFFFFFFFh
0x180026fea  inc     rax
0x180026fed  cmp     [rdx+rax*2], r8w
0x180026ff2  jnz     short loc_180026FEA
0x180026ff4  lea     ecx, ds:2[rax*2]
0x180026ffb  jmp     short loc_180027002
0x180026ffd  mov     ecx, 0Ah
0x180027002  mov     r9d, 4
0x180027008  mov     [rbp+57h+var_58], ecx
0x18002700b  test    rbx, rbx
0x18002700e  mov     [rbp+57h+var_54], r8d
0x180027012  lea     rdx, aNull; "NULL"
0x180027019  mov     [rbp+57h+var_48], r9
0x18002701d  mov     rax, rbx
0x180027020  mov     [rbp+57h+var_38], r9
0x180027024  cmovz   rax, rdx
0x180027028  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_DEBUG
0x18002702f  mov     [rbp+57h+var_60], rax
0x180027033  lea     rax, [rbp+57h+var_80]
0x180027037  mov     [rbp+57h+var_50], rax
0x18002703b  lea     rax, [rbp+57h+var_78]
0x18002703f  mov     [rbp+57h+var_40], rax
0x180027043  lea     rax, [rbp+57h+var_70]
0x180027047  mov     [rsp+0B0h+var_90], rax
0x18002704c  call    McGenEventWrite_EventWriteTransfer
0x180027051  mov     r9d, edi
0x180027054  mov     dword ptr [rsp+0B0h+var_90], esi
0x180027058  mov     r8, rbx
0x18002705b  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x180027062  mov     ecx, r14d; Level
0x180027065  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x18002706a  mov     rcx, [rbp+57h+var_30]
0x18002706e  xor     rcx, rsp; StackCookie
0x180027071  call    __security_check_cookie
0x180027076  add     rsp, 90h
0x18002707d  pop     r14
0x18002707f  pop     rdi
0x180027080  pop     rsi
0x180027081  pop     rbx
0x180027082  pop     rbp
0x180027083  retn
```
