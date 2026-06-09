# UmpoRundownPowerSettingProfileValue

- ea: `0x180007254`
- end: `0x18000742d`
- name: `UmpoRundownPowerSettingProfileValue`
- size: `473`
- prototype: `__int64 __fastcall(UUID *, UUID *, __int64, UUID *, char, char)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007440`

## callees

- `0x18000681c`
- `0x180007254`
- `0x1800083d0`
- `0x180010070`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000736e`
- `ntdll!RtlFreeHeap` at `0x18000736e`
- `ntdll!EtwEventWrite` at `0x180007422`
- `ntdll!EtwEventWrite` at `0x180007422`

## pseudocode

```c
__int64 __fastcall UmpoRundownPowerSettingProfileValue(UUID *a1, UUID *a2, __int64 a3, UUID *a4, char a5, char a6)
{
  unsigned int v10; // edi
  unsigned int PowerSettingValue; // eax
  PVOID v13; // rbx
  DWORD v14; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v15; // [rsp+64h] [rbp-9Ch] BYREF
  BOOL v16; // [rsp+6Ch] [rbp-94h] BYREF
  int v17; // [rsp+70h] [rbp-90h] BYREF
  PVOID P; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v19[17]; // [rsp+80h] [rbp-80h] BYREF
  DWORD v20; // [rsp+108h] [rbp+8h]
  int v21; // [rsp+10Ch] [rbp+Ch]
  char *v22; // [rsp+110h] [rbp+10h]
  __int64 v23; // [rsp+118h] [rbp+18h]

  v15 = 0;
  P = 0;
  v17 = 0;
  v16 = a6 != 0;
  v14 = 4;
  v10 = UmpoReadFromSystemPowerKey(a1, a2, a3, a4, a5, 8 - v16, 0, 0, (BYTE *)&v15, &v14, (int *)&v15 + 1);
  if ( !v10 )
  {
    PowerSettingValue = UmpoGetPowerSettingValue((__int64)a1, a2, v15, (__int64)&P, (__int64)&v14);
    v13 = P;
    v10 = PowerSettingValue;
    if ( !PowerSettingValue )
    {
      v19[8] = &v16;
      v19[0] = a3;
      v19[10] = &v15;
      v19[1] = 16;
      v19[12] = &v17;
      v19[2] = a2;
      v19[14] = &v14;
      v20 = v14;
      v22 = (char *)&v15 + 4;
      v19[3] = 16;
      v19[4] = a4;
      v19[5] = 16;
      v19[6] = a1;
      v19[7] = 16;
      v19[9] = 4;
      v19[11] = 4;
      v19[13] = 4;
      v19[15] = 4;
      v19[16] = P;
      v21 = 0;
      v23 = 4;
      EtwEventWrite(UmpoProviderHandle, UMPO_EVT_RUNDOWN_POWER_PROFILE_SETTING, 10, v19);
    }
    if ( v13 )
      RtlFreeHeap(UmpoHeapHandle, 0, v13);
  }
  return v10;
}

```

## disassembly

```asm
0x180007254  push    rbp
0x180007256  push    rbx
0x180007257  push    rsi
0x180007258  push    rdi
0x180007259  push    r12
0x18000725b  push    r13
0x18000725d  push    r14
0x18000725f  push    r15
0x180007261  lea     rbp, [rsp-38h]
0x180007266  sub     rsp, 138h
0x18000726d  mov     rax, cs:__security_cookie
0x180007274  xor     rax, rsp
0x180007277  mov     [rbp+70h+var_50], rax
0x18000727b  mov     bl, [rbp+70h+arg_20]
0x180007281  xor     r13d, r13d
0x180007284  mov     rsi, rcx
0x180007287  mov     dword ptr [rsp+170h+var_10C+4], r13d
0x18000728c  mov     cl, [rbp+70h+arg_28]
0x180007292  mov     eax, r13d
0x180007295  test    cl, cl
0x180007297  mov     dword ptr [rsp+170h+var_10C], r13d
0x18000729c  mov     r15, r9
0x18000729f  mov     [rsp+170h+P], r13
0x1800072a4  setnz   al
0x1800072a7  mov     [rsp+170h+var_100], r13d
0x1800072ac  neg     cl
0x1800072ae  mov     [rsp+170h+var_104], eax
0x1800072b2  lea     rcx, [rsp+170h+var_10C+4]
0x1800072b7  mov     [rsp+170h+var_110], 4
0x1800072bf  mov     [rsp+170h+var_120], rcx; __int64
0x1800072c4  sbb     eax, eax
0x1800072c6  lea     rcx, [rsp+170h+var_110]
0x1800072cb  add     eax, 8
0x1800072ce  mov     [rsp+170h+var_128], rcx; LPDWORD
0x1800072d3  mov     r12, r8
0x1800072d6  lea     rcx, [rsp+170h+var_10C]
0x1800072db  mov     r14, rdx
0x1800072de  mov     [rsp+170h+var_130], rcx; __int64
0x1800072e3  mov     rcx, rsi; __int64
0x1800072e6  mov     [rsp+170h+var_138], r13d; int
0x1800072eb  mov     [rsp+170h+var_140], r13; __int64
0x1800072f0  mov     dword ptr [rsp+170h+var_148], eax; int
0x1800072f4  mov     [rsp+170h+var_150], bl; char
0x1800072f8  call    UmpoReadFromSystemPowerKey
0x1800072fd  mov     edi, eax
0x1800072ff  test    eax, eax
0x180007301  jz      short loc_180007325
0x180007303  mov     eax, edi
0x180007305  mov     rcx, [rbp+70h+var_50]
0x180007309  xor     rcx, rsp; StackCookie
0x18000730c  call    __security_check_cookie
0x180007311  add     rsp, 138h
0x180007318  pop     r15
0x18000731a  pop     r14
0x18000731c  pop     r13
0x18000731e  pop     r12
0x180007320  pop     rdi
0x180007321  pop     rsi
0x180007322  pop     rbx
0x180007323  pop     rbp
0x180007324  retn
0x180007325  lea     rax, [rsp+170h+var_110]
0x18000732a  mov     r9b, bl
0x18000732d  mov     [rsp+170h+var_140], rax; __int64
0x180007332  mov     r8, r15
0x180007335  lea     rax, [rsp+170h+P]
0x18000733a  mov     rdx, r14; Uuid1
0x18000733d  mov     [rsp+170h+var_148], rax; __int64
0x180007342  mov     rcx, rsi; __int64
0x180007345  mov     eax, dword ptr [rsp+170h+var_10C]
0x180007349  mov     dword ptr [rsp+170h+var_150], eax; int
0x18000734d  call    UmpoGetPowerSettingValue
0x180007352  mov     rbx, [rsp+170h+P]
0x180007357  mov     edi, eax
0x180007359  test    eax, eax
0x18000735b  jz      short loc_180007376
0x18000735d  test    rbx, rbx
0x180007360  jz      short loc_180007303
0x180007362  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180007369  mov     r8, rbx; P
0x18000736c  xor     edx, edx; Flags
0x18000736e  call    cs:__imp_RtlFreeHeap
0x180007374  jmp     short loc_180007303
0x180007376  mov     rcx, cs:UmpoProviderHandle
0x18000737d  lea     rax, [rsp+170h+var_104]
0x180007382  mov     [rbp+70h+var_B0], rax
0x180007386  lea     r9, [rbp+70h+var_F0]
0x18000738a  lea     rax, [rsp+170h+var_10C]
0x18000738f  mov     [rbp+70h+var_F0], r12
0x180007393  mov     [rbp+70h+var_A0], rax
0x180007397  lea     rdx, UMPO_EVT_RUNDOWN_POWER_PROFILE_SETTING
0x18000739e  lea     rax, [rsp+170h+var_100]
0x1800073a3  mov     [rbp+70h+var_E8], 10h
0x1800073ab  mov     [rbp+70h+var_90], rax
0x1800073af  mov     r8d, 0Ah
0x1800073b5  lea     rax, [rsp+170h+var_110]
0x1800073ba  mov     [rbp+70h+var_E0], r14
0x1800073be  mov     [rbp+70h+var_80], rax
0x1800073c2  mov     eax, [rsp+170h+var_110]
0x1800073c6  mov     [rbp+70h+var_68], eax
0x1800073c9  lea     rax, [rsp+170h+var_10C+4]
0x1800073ce  mov     [rbp+70h+var_60], rax
0x1800073d2  mov     [rbp+70h+var_D8], 10h
0x1800073da  mov     [rbp+70h+var_D0], r15
0x1800073de  mov     [rbp+70h+var_C8], 10h
0x1800073e6  mov     [rbp+70h+var_C0], rsi
0x1800073ea  mov     [rbp+70h+var_B8], 10h
0x1800073f2  mov     [rbp+70h+var_A8], 4
0x1800073fa  mov     [rbp+70h+var_98], 4
0x180007402  mov     [rbp+70h+var_88], 4
0x18000740a  mov     [rbp+70h+var_78], 4
0x180007412  mov     [rbp+70h+var_70], rbx
0x180007416  mov     [rbp+70h+var_64], r13d
0x18000741a  mov     [rbp+70h+var_58], 4
0x180007422  call    cs:__imp_EtwEventWrite
0x180007428  jmp     loc_18000735D
```
