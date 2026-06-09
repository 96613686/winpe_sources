# TmpTraceTransactionHeuristicCorruption

- ea: `0x14000f82c`
- end: `0x14000f93b`
- name: `TmpTraceTransactionHeuristicCorruption`
- size: `271`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400108c0`
- `0x140016110`
- `0x1400161c0`

## callees

- `0x1400024e0`
- `0x14000f82c`

## import_xrefs

- `ntoskrnl!EtwWrite` at `0x14000f919`
- `ntoskrnl!EtwWrite` at `0x14000f919`

## pseudocode

```c
NTSTATUS __fastcall TmpTraceTransactionHeuristicCorruption(__int64 a1)
{
  NTSTATUS result; // eax
  __int64 v3; // r8
  ULONGLONG v4; // rax
  int v5; // ecx
  int v6; // edx
  __int16 v7; // [rsp+30h] [rbp-29h] BYREF
  __int16 v8; // [rsp+34h] [rbp-25h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-19h] BYREF
  __int16 *v10; // [rsp+50h] [rbp-9h]
  __int64 v11; // [rsp+58h] [rbp-1h]
  __int64 v12; // [rsp+60h] [rbp+7h]
  int v13; // [rsp+68h] [rbp+Fh]
  int v14; // [rsp+6Ch] [rbp+13h]
  __int64 v15; // [rsp+70h] [rbp+17h]
  __int64 v16; // [rsp+78h] [rbp+1Fh]
  __int16 *v17; // [rsp+80h] [rbp+27h]
  __int64 v18; // [rsp+88h] [rbp+2Fh]
  __int64 v19; // [rsp+90h] [rbp+37h]
  int v20; // [rsp+98h] [rbp+3Fh]
  int v21; // [rsp+9Ch] [rbp+43h]

  result = 0;
  v7 = 0;
  if ( TmpEtwHandle )
  {
    v3 = *(_QWORD *)(a1 + 512);
    v4 = a1 + 176;
    v5 = *(unsigned __int16 *)(a1 + 304);
    UserData.Ptr = v4;
    v8 = (unsigned __int16)v5 >> 1;
    v10 = &v8;
    v12 = *(_QWORD *)(a1 + 312);
    v15 = v3 + 112;
    v13 = v5;
    *(_QWORD *)&UserData.Size = 16;
    v11 = 2;
    v14 = 0;
    v16 = 16;
    v7 = *(_WORD *)(v3 + 136) >> 1;
    v17 = &v7;
    v18 = 2;
    v6 = *(unsigned __int16 *)(v3 + 136);
    v19 = *(_QWORD *)(v3 + 144);
    v20 = v6;
    v21 = 0;
    return EtwWrite(TmpEtwHandle, &KTM_ETW_EVENT_TRANSACTION_HEURISTIC_CORRUPTION, 0, 6u, &UserData);
  }
  return result;
}

```

## disassembly

```asm
0x14000f82c  push    rbp
0x14000f82e  lea     rbp, [rsp-57h]
0x14000f833  sub     rsp, 0B0h
0x14000f83a  mov     rax, cs:__security_cookie
0x14000f841  xor     rax, rsp
0x14000f844  mov     [rbp+57h+var_10], rax
0x14000f848  mov     r10, cs:TmpEtwHandle
0x14000f84f  xor     eax, eax
0x14000f851  mov     [rbp+57h+var_80], ax
0x14000f855  mov     rdx, rcx
0x14000f858  test    r10, r10
0x14000f85b  jz      loc_14000F925
0x14000f861  mov     r8, [rcx+200h]
0x14000f868  lea     rax, [rcx+0B0h]
0x14000f86f  movzx   ecx, word ptr [rcx+130h]
0x14000f876  mov     r9d, 6; UserDataCount
0x14000f87c  mov     [rbp+57h+var_70.Ptr], rax
0x14000f880  movzx   eax, cx
0x14000f883  shr     ax, 1
0x14000f886  mov     [rbp+57h+var_7C], ax
0x14000f88a  lea     rax, [rbp+57h+var_7C]
0x14000f88e  mov     [rbp+57h+var_60], rax
0x14000f892  mov     rax, [rdx+138h]
0x14000f899  mov     [rbp+57h+var_50], rax
0x14000f89d  lea     rax, [r8+70h]
0x14000f8a1  mov     [rbp+57h+var_40], rax
0x14000f8a5  mov     [rbp+57h+var_48], ecx
0x14000f8a8  mov     rcx, r10; RegHandle
0x14000f8ab  mov     qword ptr [rbp+57h+var_70.Size], 10h
0x14000f8b3  mov     [rbp+57h+var_58], 2
0x14000f8bb  mov     [rbp+57h+var_44], 0
0x14000f8c2  mov     [rbp+57h+var_38], 10h
0x14000f8ca  movzx   eax, word ptr [r8+88h]
0x14000f8d2  shr     ax, 1
0x14000f8d5  mov     [rbp+57h+var_80], ax
0x14000f8d9  lea     rax, [rbp+57h+var_80]
0x14000f8dd  mov     [rbp+57h+var_30], rax
0x14000f8e1  mov     [rbp+57h+var_28], 2
0x14000f8e9  mov     rax, [r8+90h]
0x14000f8f0  movzx   edx, word ptr [r8+88h]
0x14000f8f8  xor     r8d, r8d; ActivityId
0x14000f8fb  mov     [rbp+57h+var_20], rax
0x14000f8ff  lea     rax, [rbp+57h+var_70]
0x14000f903  mov     [rbp+57h+var_18], edx
0x14000f906  lea     rdx, KTM_ETW_EVENT_TRANSACTION_HEURISTIC_CORRUPTION; EventDescriptor
0x14000f90d  mov     [rsp+0B0h+UserData], rax; UserData
0x14000f912  mov     [rbp+57h+var_14], 0
0x14000f919  call    cs:__imp_EtwWrite
0x14000f920  nop     dword ptr [rax+rax+00h]
0x14000f925  mov     rcx, [rbp+57h+var_10]
0x14000f929  xor     rcx, rsp; StackCookie
0x14000f92c  call    __security_check_cookie
0x14000f931  add     rsp, 0B0h
0x14000f938  pop     rbp
0x14000f939  retn
```
