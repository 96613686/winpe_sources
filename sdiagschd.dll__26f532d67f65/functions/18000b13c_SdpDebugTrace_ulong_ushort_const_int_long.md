# SdpDebugTrace(ulong,ushort const *,int,long)

- ea: `0x18000b13c`
- end: `0x18000b22c`
- name: `?SdpDebugTrace@@YAXKPEBGHJ@Z`
- size: `240`
- prototype: `void __fastcall(ULONG Level, const unsigned __int16 *, int, int)`
- caller_count: `52`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800025f0`
- `0x180002730`
- `0x180002850`
- `0x1800028c4`
- `0x180002b88`
- `0x180002de0`
- `0x180003100`
- `0x180003384`
- `0x180003554`
- `0x180003a94`
- `0x180003e10`
- `0x1800040b4`
- `0x180004340`
- `0x18000440c`
- `0x180004590`
- `0x1800046ac`
- `0x1800048bc`
- `0x180004b8c`
- `0x180004c48`
- `0x180004fd4`
- `0x1800050c0`
- `0x180005260`
- `0x180005404`
- `0x180005974`
- `0x180005b70`
- `0x180005d78`
- `0x180005e30`
- `0x180005f60`
- `0x1800060bc`
- `0x1800062c4`
- `0x180006770`
- `0x180006940`
- `0x180006ba8`
- `0x180006f20`
- `0x1800072cc`
- `0x1800073ec`
- `0x180007580`
- `0x180007680`
- `0x1800076e0`
- `0x180007810`
- `0x180007970`
- `0x180007a48`
- `0x180007c60`
- `0x180008038`
- `0x1800081f0`
- `0x1800083d0`
- `0x18000b234`
- `0x18000b300`
- `0x18000b498`
- `0x18000b608`

## callees

- `0x1800056b4`
- `0x18000b094`
- `0x18000b13c`
- `0x18000c860`

## pseudocode

```c
void __fastcall SdpDebugTrace(ULONG Level, const unsigned __int16 *a2, unsigned int a3, int a4)
{
  __int64 v8; // rax
  int v9; // ecx
  const wchar_t *v10; // rax
  __int64 v11; // [rsp+20h] [rbp-39h]
  unsigned int v12; // [rsp+30h] [rbp-29h] BYREF
  int v13; // [rsp+38h] [rbp-21h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+40h] [rbp-19h] BYREF
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
      v9 = 2 * v8 + 2;
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
    McGenEventWrite_EventWriteTransfer(
      SCRIPTED_DIAGNOSTICS_PROVIDER_Context,
      &SCRIPTED_DIAGNOSTICS_EVENT_DEBUG,
      0,
      4u,
      &v14);
  }
  LODWORD(v11) = a4;
  SdpDebugPrint(Level, "SDIAG: %ws:%d - hr = 0x%08X\n", a2, a3, v11);
}

```

## disassembly

```asm
0x18000b13c  push    rbp
0x18000b13e  push    rbx
0x18000b13f  push    rsi
0x18000b140  push    rdi
0x18000b141  push    r14
0x18000b143  lea     rbp, [rsp-37h]
0x18000b148  sub     rsp, 90h
0x18000b14f  mov     rax, cs:__security_cookie
0x18000b156  xor     rax, rsp
0x18000b159  mov     [rbp+57h+var_30], rax
0x18000b15d  test    cs:Microsoft_Windows_Diagnosis_ScriptedEnableBits, 8
0x18000b164  mov     esi, r9d
0x18000b167  mov     edi, r8d
0x18000b16a  mov     rbx, rdx
0x18000b16d  mov     r14d, ecx
0x18000b170  jz      loc_18000B1F8
0x18000b176  mov     [rbp+57h+var_80], r8d
0x18000b17a  xor     r8d, r8d
0x18000b17d  mov     [rbp+57h+var_78], r9d
0x18000b181  test    rdx, rdx
0x18000b184  jz      short loc_18000B19D
0x18000b186  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b18a  inc     rax
0x18000b18d  cmp     [rdx+rax*2], r8w
0x18000b192  jnz     short loc_18000B18A
0x18000b194  lea     ecx, ds:2[rax*2]
0x18000b19b  jmp     short loc_18000B1A2
0x18000b19d  mov     ecx, 0Ah
0x18000b1a2  mov     r9d, 4
0x18000b1a8  mov     [rbp+57h+var_58], ecx
0x18000b1ab  test    rbx, rbx
0x18000b1ae  mov     [rbp+57h+var_54], r8d
0x18000b1b2  lea     rdx, aNull; "NULL"
0x18000b1b9  mov     [rbp+57h+var_48], r9
0x18000b1bd  mov     rax, rbx
0x18000b1c0  mov     [rbp+57h+var_38], r9
0x18000b1c4  cmovz   rax, rdx
0x18000b1c8  lea     rcx, SCRIPTED_DIAGNOSTICS_PROVIDER_Context
0x18000b1cf  mov     [rbp+57h+var_60], rax
0x18000b1d3  lea     rdx, SCRIPTED_DIAGNOSTICS_EVENT_DEBUG
0x18000b1da  lea     rax, [rbp+57h+var_80]
0x18000b1de  mov     [rbp+57h+var_50], rax
0x18000b1e2  lea     rax, [rbp+57h+var_78]
0x18000b1e6  mov     [rbp+57h+var_40], rax
0x18000b1ea  lea     rax, [rbp+57h+var_70]
0x18000b1ee  mov     [rsp+0B0h+var_90], rax
0x18000b1f3  call    McGenEventWrite_EventWriteTransfer
0x18000b1f8  mov     r9d, edi
0x18000b1fb  mov     dword ptr [rsp+0B0h+var_90], esi
0x18000b1ff  mov     r8, rbx
0x18000b202  lea     rdx, aSdiagWsDHr0x08; "SDIAG: %ws:%d - hr = 0x%08X\n"
0x18000b209  mov     ecx, r14d; Level
0x18000b20c  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x18000b211  mov     rcx, [rbp+57h+var_30]
0x18000b215  xor     rcx, rsp; StackCookie
0x18000b218  call    __security_check_cookie
0x18000b21d  add     rsp, 90h
0x18000b224  pop     r14
0x18000b226  pop     rdi
0x18000b227  pop     rsi
0x18000b228  pop     rbx
0x18000b229  pop     rbp
0x18000b22a  retn
```
