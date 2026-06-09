# SLGetGenuineInformationEx

- ea: `0x180041130`
- end: `0x180041379`
- name: `SLGetGenuineInformationEx`
- size: `585`
- prototype: `HRESULT __stdcall(const SLID *pAppId, PCWSTR pwszValueName, SLDATATYPE *peDataType, UINT *pcbValue, BYTE **ppbValue)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation`

## callers

- `0x1800305dc`

## callees

- `0x180004ca0`
- `0x180006c10`
- `0x18000760c`
- `0x180008954`
- `0x18003fa4c`
- `0x1800400bc`
- `0x180040570`
- `0x180041130`
- `0x180042514`
- `0x1800427f4`
- `0x180042acc`
- `0x180042db0`
- `0x180043088`
- `0x180043364`
- `0x18004362c`
- `0x180043900`
- `0x180043bd8`
- `0x180043eac`
- `0x18006ef52`

## import_xrefs

- `sppc!SLOpen` at `0x18004121e`
- `sppc!SLOpen` at `0x18004121e`
- `sppc!SLGetGenuineInformation` at `0x1800411ea`
- `sppc!SLGetGenuineInformation` at `0x18004130c`
- `sppc!SLGetGenuineInformation` at `0x1800411ea`
- `sppc!SLGetGenuineInformation` at `0x18004130c`

## pseudocode

```c
HRESULT __stdcall SLGetGenuineInformationEx(
        const SLID *pAppId,
        PCWSTR pwszValueName,
        SLDATATYPE *peDataType,
        UINT *pcbValue,
        BYTE **ppbValue)
{
  __int64 v9; // rcx
  int v10; // ebx
  HSLC phSLC; // [rsp+38h] [rbp-18h] BYREF
  SLID *pQueryId[2]; // [rsp+40h] [rbp-10h] BYREF

  phSLC = 0;
  sub_18004362C(&dword_18008097C, qword_18008D478);
  pQueryId[0] = 0;
  sub_180042514(qword_180082C10, &dword_18008D69C);
  if ( !pAppId )
    goto LABEL_2;
  if ( !pwszValueName )
  {
    sub_180043088(qword_1800841E0, byte_18008CE70);
LABEL_2:
    v9 = 2147942487LL;
LABEL_3:
    v10 = v9;
LABEL_15:
    sub_180004CA0(v9);
    goto LABEL_16;
  }
  if ( !pcbValue || !ppbValue )
    goto LABEL_2;
  v10 = SLGetGenuineInformation(pAppId, pwszValueName, peDataType, pcbValue, ppbValue);
  if ( v10 == -1073418222 && !wcsncmp(pwszValueName, L"SL_GET_GENUINE_AUTHZ", 0x14u) )
  {
    v10 = SLOpen(&phSLC);
    if ( v10 >= 0 )
    {
      sub_180042ACC(byte_180081DB0, byte_18008E218);
      v10 = sub_18003FA4C(phSLC, (SLID *)pAppId, (__int64)pQueryId);
      sub_1800427F4(qword_180081960, byte_18008E1B0);
      if ( v10 >= 0 )
      {
        v9 = 3221549078LL;
        goto LABEL_3;
      }
    }
    else
    {
      sub_180043BD8(byte_180084F20, qword_18008DB48);
    }
    v9 = (unsigned int)v10;
    goto LABEL_15;
  }
LABEL_16:
  sub_180006C10((unsigned int)v10);
  sub_180042DB0(byte_180082190, qword_18008CD48);
  sub_18000760C(pQueryId);
  sub_180008954(&phSLC);
  return v10;
}

```

## disassembly

```asm
0x180041130  mov     [rsp-28h+arg_8], rbx
0x180041135  mov     [rsp-28h+arg_10], rsi
0x18004113a  push    rbp
0x18004113b  push    rdi
0x18004113c  push    r12
0x18004113e  push    r14
0x180041140  push    r15
0x180041142  mov     rbp, rsp
0x180041145  sub     rsp, 50h
0x180041149  mov     rdi, rdx
0x18004114c  mov     [rbp+phSLC], 0
0x180041154  mov     r15, rcx
0x180041157  lea     rdx, qword_18008D478
0x18004115e  lea     rcx, dword_18008097C
0x180041165  mov     r14, r9
0x180041168  mov     r12, r8
0x18004116b  call    sub_18004362C
0x180041170  lea     rdx, dword_18008D69C
0x180041177  mov     [rbp+pQueryId], 0
0x18004117f  lea     rcx, qword_180082C10
0x180041186  mov     [rbp+arg_0], 0
0x18004118d  mov     [rbp+var_20], 0
0x180041194  mov     [rbp+var_1C], 0
0x18004119b  call    sub_180042514
0x1800411a0  test    r15, r15
0x1800411a3  jnz     short loc_1800411B1
0x1800411a5  mov     ecx, 80070057h
0x1800411aa  mov     ebx, ecx
0x1800411ac  jmp     loc_18004132D
0x1800411b1  test    rdi, rdi
0x1800411b4  jnz     short loc_1800411CB
0x1800411b6  lea     rdx, byte_18008CE70
0x1800411bd  lea     rcx, qword_1800841E0
0x1800411c4  call    sub_180043088
0x1800411c9  jmp     short loc_1800411A5
0x1800411cb  test    r14, r14
0x1800411ce  jz      short loc_1800411A5
0x1800411d0  mov     rsi, [rbp+ppbValue]
0x1800411d4  test    rsi, rsi
0x1800411d7  jz      short loc_1800411A5
0x1800411d9  mov     r9, r14; pcbValue
0x1800411dc  mov     [rsp+50h+var_30], rsi; ppbValue
0x1800411e1  mov     r8, r12; peDataType
0x1800411e4  mov     rdx, rdi; pwszValueName
0x1800411e7  mov     rcx, r15; pQueryId
0x1800411ea  call    cs:SLGetGenuineInformation
0x1800411f0  mov     ebx, eax
0x1800411f2  cmp     eax, 0C004F012h
0x1800411f7  jnz     loc_180041332
0x1800411fd  mov     r8d, 14h; MaxCount
0x180041203  lea     rdx, aSlGetGenuineAu; "SL_GET_GENUINE_AUTHZ"
0x18004120a  mov     rcx, rdi; String1
0x18004120d  call    wcsncmp
0x180041212  test    eax, eax
0x180041214  jnz     loc_180041332
0x18004121a  lea     rcx, [rbp+phSLC]; phSLC
0x18004121e  call    cs:SLOpen
0x180041224  mov     ebx, eax
0x180041226  test    eax, eax
0x180041228  jns     short loc_180041242
0x18004122a  lea     rdx, qword_18008DB48
0x180041231  lea     rcx, byte_180084F20
0x180041238  call    sub_180043BD8
0x18004123d  jmp     loc_18004132B
0x180041242  lea     rdx, byte_18008E218
0x180041249  lea     rcx, byte_180081DB0
0x180041250  call    sub_180042ACC
0x180041255  mov     rcx, [rbp+phSLC]; hSLC
0x180041259  lea     rax, [rbp+pQueryId]
0x18004125d  lea     r9, [rbp+arg_0]
0x180041261  mov     [rsp+50h+var_30], rax; __int64
0x180041266  mov     rdx, r15; pQueryId
0x180041269  call    sub_18003FA4C
0x18004126e  lea     rdx, byte_18008E1B0
0x180041275  mov     ebx, eax
0x180041277  lea     rcx, qword_180081960
0x18004127e  call    sub_1800427F4
0x180041283  test    ebx, ebx
0x180041285  js      loc_18004132B
0x18004128b  cmp     [rbp+arg_0], 1
0x18004128f  jz      short loc_18004129B
0x180041291  mov     ecx, 0C004F016h
0x180041296  jmp     loc_1800411AA
0x18004129b  mov     rdx, [rbp+pQueryId]; pQueryId
0x18004129f  lea     r9, [rbp+var_1C]
0x1800412a3  mov     rcx, [rbp+phSLC]; hSLC
0x1800412a7  lea     r8, [rbp+var_20]
0x1800412ab  call    sub_1800400BC
0x1800412b0  lea     rdx, byte_18008D808
0x1800412b7  mov     ebx, eax
0x1800412b9  lea     rcx, byte_180084CA8
0x1800412c0  call    sub_180043364
0x1800412c5  test    ebx, ebx
0x1800412c7  js      short loc_18004132B
0x1800412c9  cmp     [rbp+var_20], 0
0x1800412cd  jz      short loc_180041291
0x1800412cf  mov     r8d, [rbp+var_1C]
0x1800412d3  mov     rdx, [rbp+pQueryId]
0x1800412d7  mov     rcx, [rbp+phSLC]
0x1800412db  call    sub_180040570
0x1800412e0  mov     ebx, eax
0x1800412e2  test    eax, eax
0x1800412e4  jns     short loc_1800412FB
0x1800412e6  lea     rdx, dword_18008E23C
0x1800412ed  lea     rcx, dword_180083F5C
0x1800412f4  call    sub_180043900
0x1800412f9  jmp     short loc_18004132B
0x1800412fb  mov     r9, r14; pcbValue
0x1800412fe  mov     [rsp+50h+var_30], rsi; ppbValue
0x180041303  mov     r8, r12; peDataType
0x180041306  mov     rdx, rdi; pwszValueName
0x180041309  mov     rcx, r15; pQueryId
0x18004130c  call    cs:SLGetGenuineInformation
0x180041312  lea     rdx, byte_18008CEA0
0x180041319  mov     ebx, eax
0x18004131b  lea     rcx, byte_180082238
0x180041322  call    sub_180043EAC
0x180041327  test    ebx, ebx
0x180041329  jns     short loc_180041332
0x18004132b  mov     ecx, ebx
0x18004132d  call    sub_180004CA0
0x180041332  mov     ecx, ebx
0x180041334  call    sub_180006C10
0x180041339  lea     rdx, qword_18008CD48
0x180041340  lea     rcx, byte_180082190
0x180041347  call    sub_180042DB0
0x18004134c  lea     rcx, [rbp+pQueryId]
0x180041350  call    sub_18000760C
0x180041355  lea     rcx, [rbp+phSLC]
0x180041359  call    sub_180008954
0x18004135e  lea     r11, [rsp+50h+var_s0]
0x180041363  mov     eax, ebx
0x180041365  mov     rbx, [r11+38h]
0x180041369  mov     rsi, [r11+40h]
0x18004136d  mov     rsp, r11
0x180041370  pop     r15
0x180041372  pop     r14
0x180041374  pop     r12
0x180041376  pop     rdi
0x180041377  pop     rbp
0x180041378  retn
```
