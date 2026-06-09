# ProcessFunctionDescriptors

- ea: `0x140026b6c`
- end: `0x140026c87`
- name: `ProcessFunctionDescriptors`
- size: `283`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, PVOID P@<rdx>, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002b010`

## callees

- `0x14000a6cc`
- `0x14000f664`
- `0x1400136b0`
- `0x140026970`
- `0x140026b6c`
- `0x140026c90`

## pseudocode

```c
__int64 __fastcall ProcessFunctionDescriptors(__int64 a1, PVOID P, unsigned int a3, _QWORD *a4, _DWORD *a5)
{
  __int64 v7; // r9
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // edx
  unsigned int v15; // edi
  int v16; // eax
  int v17; // edx
  size_t Size; // [rsp+30h] [rbp-48h]

  *a4 = 0;
  v7 = a3;
  v11 = *(_QWORD *)(a1 + 56);
  v12 = *(_QWORD *)(a1 + 88);
  *a5 = 0;
  v13 = ValidateCallbackData(v12, v11, P, v7);
  v15 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v14,
        8,
        10,
        (__int64)WPP_e8749e7517b2302104950dba271a6a56_Traceguids,
        v13);
    }
    LODWORD(Size) = *(unsigned __int16 *)(*(_QWORD *)(a1 + 48) + 2LL);
    RecordStartFailData(a1, v15, 0, -1610612727, 1179403074, *(void **)(a1 + 48), Size);
LABEL_8:
    CleanFunctionDescriptorArray(P);
    return v15;
  }
  v16 = ProcessCallbackData(a1, a4, a5, P, a3);
  v15 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1 + 1368),
        v17,
        8,
        11,
        (__int64)WPP_e8749e7517b2302104950dba271a6a56_Traceguids,
        v16);
    }
    goto LABEL_8;
  }
  return v15;
}

```

## disassembly

```asm
0x140026b6c  push    rbx
0x140026b6e  push    rbp
0x140026b6f  push    rsi
0x140026b70  push    rdi
0x140026b71  push    r14
0x140026b73  push    r15
0x140026b75  sub     rsp, 48h
0x140026b79  mov     r15, [rsp+78h+arg_20]
0x140026b81  mov     r14, r9
0x140026b84  mov     qword ptr [r9], 0
0x140026b8b  mov     esi, r8d
0x140026b8e  mov     r9d, r8d
0x140026b91  mov     rbp, rdx
0x140026b94  mov     r8, rdx
0x140026b97  mov     rbx, rcx
0x140026b9a  mov     rdx, [rcx+38h]
0x140026b9e  mov     rcx, [rcx+58h]
0x140026ba2  mov     dword ptr [r15], 0
0x140026ba9  call    ValidateCallbackData
0x140026bae  mov     edi, eax
0x140026bb0  test    eax, eax
0x140026bb2  jns     short loc_140026C1A
0x140026bb4  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140026bbb  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140026bc2  jz      short loc_140026BEC
0x140026bc4  mov     r9d, 0Ah
0x140026bca  mov     dword ptr [rsp+78h+Src], eax
0x140026bce  lea     rcx, WPP_e8749e7517b2302104950dba271a6a56_Traceguids
0x140026bd5  mov     dl, 2
0x140026bd7  mov     qword ptr [rsp+78h+var_58], rcx
0x140026bdc  mov     rcx, [rbx+558h]
0x140026be3  lea     r8d, [r9-2]
0x140026be7  call    WPP_RECORDER_SF_d
0x140026bec  mov     rcx, [rbx+30h]
0x140026bf0  mov     r9d, 0A0000009h; int
0x140026bf6  xor     r8d, r8d; int
0x140026bf9  mov     edx, edi; int
0x140026bfb  movzx   eax, word ptr [rcx+2]
0x140026bff  mov     dword ptr [rsp+78h+Size], eax; Size
0x140026c03  mov     [rsp+78h+Src], rcx; Src
0x140026c08  mov     rcx, rbx; int
0x140026c0b  mov     [rsp+78h+var_58], 464C4342h; int
0x140026c13  call    RecordStartFailData
0x140026c18  jmp     short loc_140026C6D
0x140026c1a  mov     r9, rbp
0x140026c1d  mov     [rsp+78h+var_58], esi
0x140026c21  mov     r8, r15
0x140026c24  mov     rdx, r14
0x140026c27  mov     rcx, rbx
0x140026c2a  call    ProcessCallbackData
0x140026c2f  mov     edi, eax
0x140026c31  test    eax, eax
0x140026c33  jns     short loc_140026C77
0x140026c35  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140026c3c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140026c43  jz      short loc_140026C6D
0x140026c45  mov     r9d, 0Bh
0x140026c4b  mov     dword ptr [rsp+78h+Src], eax
0x140026c4f  lea     rcx, WPP_e8749e7517b2302104950dba271a6a56_Traceguids
0x140026c56  mov     dl, 2
0x140026c58  mov     qword ptr [rsp+78h+var_58], rcx
0x140026c5d  mov     rcx, [rbx+558h]
0x140026c64  lea     r8d, [r9-3]
0x140026c68  call    WPP_RECORDER_SF_d
0x140026c6d  mov     edx, esi
0x140026c6f  mov     rcx, rbp; P
0x140026c72  call    CleanFunctionDescriptorArray
0x140026c77  mov     eax, edi
0x140026c79  add     rsp, 48h
0x140026c7d  pop     r15
0x140026c7f  pop     r14
0x140026c81  pop     rdi
0x140026c82  pop     rsi
0x140026c83  pop     rbp
0x140026c84  pop     rbx
0x140026c85  retn
```
