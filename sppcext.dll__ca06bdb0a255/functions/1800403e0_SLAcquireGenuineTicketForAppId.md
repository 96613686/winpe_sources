# SLAcquireGenuineTicketForAppId

- ea: `0x1800403e0`
- end: `0x180040569`
- name: `SLAcquireGenuineTicketForAppId`
- size: `393`
- prototype: `__int64 __fastcall(SLID *pQueryId)`
- caller_count: `0`
- callee_count: `17`
- tags: ``

## callees

- `0x180004ca0`
- `0x180006c10`
- `0x18000760c`
- `0x180008954`
- `0x18003fa4c`
- `0x1800403e0`
- `0x180040570`
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

## import_xrefs

- `sppc!SLOpen` at `0x180040445`
- `sppc!SLOpen` at `0x180040445`

## pseudocode

```c
__int64 __fastcall SLAcquireGenuineTicketForAppId(SLID *pQueryId)
{
  HRESULT v2; // ebx
  HSLC phSLC; // [rsp+58h] [rbp+28h] BYREF
  __int64 v5; // [rsp+60h] [rbp+30h] BYREF

  phSLC = 0;
  sub_180042514(&dword_180084A74, &dword_18008CEBC);
  v5 = 0;
  if ( pQueryId )
  {
    v2 = SLOpen(&phSLC);
    sub_1800427F4(byte_180084FD8, &dword_18008DC1C);
    if ( v2 < 0 )
    {
      sub_180042DB0(byte_180083BD0, byte_18008E180);
      sub_180004CA0((unsigned int)v2);
      sub_180043900(qword_180080B40, &dword_18008D63C);
      goto LABEL_9;
    }
    v2 = sub_18003FA4C(phSLC, pQueryId, (__int64)&v5);
    sub_180043364(qword_180083BD8, qword_18008CEA8);
    if ( v2 >= 0 )
    {
      sub_180043EAC(byte_180082BF0, qword_18008D618);
      v2 = -1073418218;
    }
    else
    {
      sub_180042ACC(&dword_180083554, byte_18008DCE0);
    }
  }
  else
  {
    v2 = -2147024809;
    sub_18004362C(&dword_180085CAC, &dword_18008D4C4);
  }
  sub_180004CA0((unsigned int)v2);
LABEL_9:
  sub_180006C10((unsigned int)v2);
  sub_18000760C(&v5);
  sub_180008954(&phSLC);
  sub_180043088(qword_1800813E0, &dword_18008DCE4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800403e0  push    rbp
0x1800403e2  push    rbx
0x1800403e3  push    rdi
0x1800403e4  mov     rbp, rsp
0x1800403e7  sub     rsp, 30h
0x1800403eb  mov     rdi, rcx
0x1800403ee  mov     [rbp+phSLC], 0
0x1800403f6  lea     rcx, dword_180084A74
0x1800403fd  lea     rdx, dword_18008CEBC
0x180040404  call    sub_180042514
0x180040409  mov     [rbp+arg_10], 0
0x180040411  mov     [rbp+arg_0], 0
0x180040418  test    rdi, rdi
0x18004041b  jnz     short loc_180040441
0x18004041d  lea     rdx, dword_18008D4C4
0x180040424  mov     ebx, 80070057h
0x180040429  lea     rcx, dword_180085CAC
0x180040430  call    sub_18004362C
0x180040435  mov     ecx, ebx
0x180040437  call    sub_180004CA0
0x18004043c  jmp     loc_180040533
0x180040441  lea     rcx, [rbp+phSLC]; phSLC
0x180040445  call    cs:SLOpen
0x18004044b  lea     rdx, dword_18008DC1C
0x180040452  mov     ebx, eax
0x180040454  lea     rcx, byte_180084FD8
0x18004045b  call    sub_1800427F4
0x180040460  test    ebx, ebx
0x180040462  jns     short loc_180040496
0x180040464  lea     rdx, byte_18008E180
0x18004046b  lea     rcx, byte_180083BD0
0x180040472  call    sub_180042DB0
0x180040477  mov     ecx, ebx
0x180040479  call    sub_180004CA0
0x18004047e  lea     rdx, dword_18008D63C
0x180040485  lea     rcx, qword_180080B40
0x18004048c  call    sub_180043900
0x180040491  jmp     loc_180040533
0x180040496  mov     rcx, [rbp+phSLC]; hSLC
0x18004049a  lea     rax, [rbp+arg_10]
0x18004049e  lea     r9, [rbp+arg_0]
0x1800404a2  mov     [rsp+30h+var_10], rax; __int64
0x1800404a7  mov     rdx, rdi; pQueryId
0x1800404aa  call    sub_18003FA4C
0x1800404af  lea     rdx, qword_18008CEA8
0x1800404b6  mov     ebx, eax
0x1800404b8  lea     rcx, qword_180083BD8
0x1800404bf  call    sub_180043364
0x1800404c4  test    ebx, ebx
0x1800404c6  jns     short loc_1800404E0
0x1800404c8  lea     rdx, byte_18008DCE0
0x1800404cf  lea     rcx, dword_180083554
0x1800404d6  call    sub_180042ACC
0x1800404db  jmp     loc_180040435
0x1800404e0  cmp     [rbp+arg_0], 1
0x1800404e4  jz      short loc_180040503
0x1800404e6  lea     rdx, qword_18008D618
0x1800404ed  lea     rcx, byte_180082BF0
0x1800404f4  call    sub_180043EAC
0x1800404f9  mov     ebx, 0C004F016h
0x1800404fe  jmp     loc_180040435
0x180040503  mov     rdx, [rbp+arg_10]
0x180040507  xor     r8d, r8d
0x18004050a  mov     rcx, [rbp+phSLC]
0x18004050e  call    sub_180040570
0x180040513  mov     ebx, eax
0x180040515  test    eax, eax
0x180040517  jns     short loc_180040533
0x180040519  mov     ecx, eax
0x18004051b  call    sub_180004CA0
0x180040520  lea     rdx, byte_18008E060
0x180040527  lea     rcx, qword_180085288
0x18004052e  call    sub_180043BD8
0x180040533  mov     ecx, ebx
0x180040535  call    sub_180006C10
0x18004053a  lea     rcx, [rbp+arg_10]
0x18004053e  call    sub_18000760C
0x180040543  lea     rcx, [rbp+phSLC]
0x180040547  call    sub_180008954
0x18004054c  lea     rdx, dword_18008DCE4
0x180040553  lea     rcx, qword_1800813E0
0x18004055a  call    sub_180043088
0x18004055f  mov     eax, ebx
0x180040561  add     rsp, 30h
0x180040565  pop     rdi
0x180040566  pop     rbx
0x180040567  pop     rbp
0x180040568  retn
```
