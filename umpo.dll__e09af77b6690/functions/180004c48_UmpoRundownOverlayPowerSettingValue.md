# UmpoRundownOverlayPowerSettingValue

- ea: `0x180004c48`
- end: `0x180004e03`
- name: `UmpoRundownOverlayPowerSettingValue`
- size: `443`
- prototype: `__int64 __fastcall(UUID *, UUID *Uuid1, UUID *, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180004bd0`

## callees

- `0x180004c48`
- `0x180005cb4`
- `0x1800083d0`
- `0x180010070`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180004d61`
- `ntdll!RtlFreeHeap` at `0x180004d61`
- `ntdll!EtwEventWrite` at `0x180004df8`
- `ntdll!EtwEventWrite` at `0x180004df8`

## pseudocode

```c
__int64 __fastcall UmpoRundownOverlayPowerSettingValue(UUID *a1, UUID *Uuid1, UUID *a3, char a4)
{
  unsigned int v7; // edi
  unsigned int PowerSettingValue; // eax
  PVOID v10; // rbx
  DWORD v11; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v12; // [rsp+54h] [rbp-ACh] BYREF
  BOOL v13; // [rsp+5Ch] [rbp-A4h] BYREF
  int v14; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v16[15]; // [rsp+70h] [rbp-90h] BYREF
  DWORD v17; // [rsp+E8h] [rbp-18h]
  int v18; // [rsp+ECh] [rbp-14h]
  char *v19; // [rsp+F0h] [rbp-10h]
  __int64 v20; // [rsp+F8h] [rbp-8h]

  v12 = 0;
  P = 0;
  v13 = a4 != 0;
  v14 = 0;
  v11 = 4;
  v7 = UmpoReadFromUserPowerKey(a1, Uuid1, a3, 1, 1, a4 == 0, 0, (BYTE *)&v12, &v11, (int *)&v12 + 1);
  if ( !v7 )
  {
    PowerSettingValue = UmpoGetPowerSettingValue((__int64)a1, Uuid1, v12, (__int64)&P, (__int64)&v11);
    v10 = P;
    v7 = PowerSettingValue;
    if ( !PowerSettingValue )
    {
      v16[6] = &v13;
      v16[0] = a1;
      v16[8] = &v12;
      v16[1] = 16;
      v16[10] = &v14;
      v16[2] = Uuid1;
      v16[12] = &v11;
      v17 = v11;
      v19 = (char *)&v12 + 4;
      v16[3] = 16;
      v16[4] = a3;
      v16[5] = 16;
      v16[7] = 4;
      v16[9] = 4;
      v16[11] = 4;
      v16[13] = 4;
      v16[14] = P;
      v18 = 0;
      v20 = 4;
      EtwEventWrite(UmpoProviderHandle, "1", 9, v16);
    }
    if ( v10 )
      RtlFreeHeap(UmpoHeapHandle, 0, v10);
  }
  return v7;
}

```

## disassembly

```asm
0x180004c48  mov     [rsp-8+arg_18], rbx
0x180004c4d  push    rbp
0x180004c4e  push    rsi
0x180004c4f  push    rdi
0x180004c50  push    r12
0x180004c52  push    r13
0x180004c54  push    r14
0x180004c56  push    r15
0x180004c58  lea     rbp, [rsp-10h]
0x180004c5d  sub     rsp, 110h
0x180004c64  mov     rax, cs:__security_cookie
0x180004c6b  xor     rax, rsp
0x180004c6e  mov     [rbp+40h+var_40], rax
0x180004c72  xor     r12d, r12d
0x180004c75  mov     rsi, rcx
0x180004c78  test    r9b, r9b
0x180004c7b  mov     dword ptr [rsp+140h+var_EC+4], r12d
0x180004c80  mov     eax, r12d
0x180004c83  mov     dword ptr [rsp+140h+var_EC], r12d
0x180004c88  setnz   al
0x180004c8b  mov     [rsp+140h+P], r12
0x180004c90  mov     [rsp+140h+var_E4], eax
0x180004c94  lea     rcx, [rsp+140h+var_EC+4]
0x180004c99  mov     [rsp+140h+var_F8], rcx; __int64
0x180004c9e  lea     r13d, [r12+4]
0x180004ca3  test    r9b, r9b
0x180004ca6  mov     [rsp+140h+var_E0], r12d
0x180004cab  mov     eax, r12d
0x180004cae  mov     [rsp+140h+var_F0], r13d
0x180004cb3  lea     rcx, [rsp+140h+var_F0]
0x180004cb8  setz    al
0x180004cbb  mov     [rsp+140h+var_100], rcx; LPDWORD
0x180004cc0  mov     r9b, 1
0x180004cc3  lea     rcx, [rsp+140h+var_EC]
0x180004cc8  mov     r15, r8
0x180004ccb  mov     [rsp+140h+var_108], rcx; __int64
0x180004cd0  mov     r14, rdx
0x180004cd3  mov     [rsp+140h+lpType], r12; lpType
0x180004cd8  mov     rcx, rsi; Uuid2
0x180004cdb  mov     dword ptr [rsp+140h+var_118], eax; int
0x180004cdf  mov     [rsp+140h+var_120], 1; char
0x180004ce4  call    UmpoReadFromUserPowerKey
0x180004ce9  mov     edi, eax
0x180004ceb  test    eax, eax
0x180004ced  jz      short loc_180004D18
0x180004cef  mov     eax, edi
0x180004cf1  mov     rcx, [rbp+40h+var_40]
0x180004cf5  xor     rcx, rsp; StackCookie
0x180004cf8  call    __security_check_cookie
0x180004cfd  mov     rbx, [rsp+140h+arg_18]
0x180004d05  add     rsp, 110h
0x180004d0c  pop     r15
0x180004d0e  pop     r14
0x180004d10  pop     r13
0x180004d12  pop     r12
0x180004d14  pop     rdi
0x180004d15  pop     rsi
0x180004d16  pop     rbp
0x180004d17  retn
0x180004d18  lea     rax, [rsp+140h+var_F0]
0x180004d1d  mov     r9b, 1
0x180004d20  mov     [rsp+140h+lpType], rax; __int64
0x180004d25  mov     r8, r15
0x180004d28  lea     rax, [rsp+140h+P]
0x180004d2d  mov     rdx, r14; Uuid1
0x180004d30  mov     [rsp+140h+var_118], rax; __int64
0x180004d35  mov     rcx, rsi; __int64
0x180004d38  mov     eax, dword ptr [rsp+140h+var_EC]
0x180004d3c  mov     dword ptr [rsp+140h+var_120], eax; int
0x180004d40  call    UmpoGetPowerSettingValue
0x180004d45  mov     rbx, [rsp+140h+P]
0x180004d4a  mov     edi, eax
0x180004d4c  test    eax, eax
0x180004d4e  jz      short loc_180004D69
0x180004d50  test    rbx, rbx
0x180004d53  jz      short loc_180004CEF
0x180004d55  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180004d5c  mov     r8, rbx; P
0x180004d5f  xor     edx, edx; Flags
0x180004d61  call    cs:__imp_RtlFreeHeap
0x180004d67  jmp     short loc_180004CEF
0x180004d69  mov     rcx, cs:UmpoProviderHandle
0x180004d70  lea     rax, [rsp+140h+var_E4]
0x180004d75  mov     [rbp+40h+var_A0], rax
0x180004d79  lea     r9, [rsp+140h+var_D0]
0x180004d7e  lea     rax, [rsp+140h+var_EC]
0x180004d83  mov     [rsp+140h+var_D0], rsi
0x180004d88  mov     [rbp+40h+var_90], rax
0x180004d8c  lea     rdx, UMPO_EVT_RUNDOWN_OVERLAY_POWER_SCHEME_SETTING; "1"
0x180004d93  lea     rax, [rsp+140h+var_E0]
0x180004d98  mov     [rsp+140h+var_C8], 10h
0x180004da1  mov     [rbp+40h+var_80], rax
0x180004da5  mov     r8d, 9
0x180004dab  lea     rax, [rsp+140h+var_F0]
0x180004db0  mov     [rbp+40h+var_C0], r14
0x180004db4  mov     [rbp+40h+var_70], rax
0x180004db8  mov     eax, [rsp+140h+var_F0]
0x180004dbc  mov     [rbp+40h+var_58], eax
0x180004dbf  lea     rax, [rsp+140h+var_EC+4]
0x180004dc4  mov     [rbp+40h+var_50], rax
0x180004dc8  mov     [rbp+40h+var_B8], 10h
0x180004dd0  mov     [rbp+40h+var_B0], r15
0x180004dd4  mov     [rbp+40h+var_A8], 10h
0x180004ddc  mov     [rbp+40h+var_98], r13
0x180004de0  mov     [rbp+40h+var_88], r13
0x180004de4  mov     [rbp+40h+var_78], r13
0x180004de8  mov     [rbp+40h+var_68], r13
0x180004dec  mov     [rbp+40h+var_60], rbx
0x180004df0  mov     [rbp+40h+var_54], r12d
0x180004df4  mov     [rbp+40h+var_48], r13
0x180004df8  call    cs:__imp_EtwEventWrite
0x180004dfe  jmp     loc_180004D50
```
