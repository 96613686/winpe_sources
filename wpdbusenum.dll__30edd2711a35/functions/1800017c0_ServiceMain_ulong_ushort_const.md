# ServiceMain(ulong,ushort * * const)

- ea: `0x1800017c0`
- end: `0x1800018b4`
- name: `?ServiceMain@@YAXKQEAPEAG@Z`
- size: `244`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800017c0`
- `0x1800018c0`
- `0x180007f28`
- `0x18000dfd4`
- `0x18000ed3c`
- `0x1800154e4`

## pseudocode

```c
void __fastcall ServiceMain(unsigned int a1, unsigned __int16 **const a2)
{
  int v4; // edi
  CPnPNotification *v5; // rsi
  unsigned int SystemTime; // eax
  unsigned int v7; // eax

  v4 = 0;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    SystemTime = GetSystemTime();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, SystemTime);
    v5 = WPP_GLOBAL_Control;
  }
  if ( a1 >= 2 && !wcscmp_0(a2[1], L"TriggerStarted") )
  {
    v4 = 1;
    if ( v5 != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_DWORD *)v5 + 7) & 0x200) != 0 )
      WPP_SF_(*((_QWORD *)v5 + 2), 16, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids);
  }
  CService::Start((CService *)&_Service, L"WpdBusEnum", v4);
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
  {
    v7 = GetSystemTime();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids, v7);
  }
}

```

## disassembly

```asm
0x1800017c0  push    rbx
0x1800017c2  push    rbp
0x1800017c3  push    rsi
0x1800017c4  push    rdi
0x1800017c5  push    r14
0x1800017c7  sub     rsp, 20h
0x1800017cb  mov     rbp, rdx
0x1800017ce  mov     ebx, ecx
0x1800017d0  xor     edi, edi
0x1800017d2  mov     rsi, cs:WPP_GLOBAL_Control
0x1800017d9  lea     r14, WPP_GLOBAL_Control
0x1800017e0  cmp     rsi, r14
0x1800017e3  jz      short loc_180001819
0x1800017e5  test    dword ptr [rsi+1Ch], 200h
0x1800017ec  jz      short loc_180001819
0x1800017ee  call    ?GetSystemTime@@YAKXZ; GetSystemTime(void)
0x1800017f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017fa  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180001801  mov     edx, 0Fh
0x180001806  mov     r9d, eax
0x180001809  mov     rcx, [rcx+10h]
0x18000180d  call    WPP_SF_d
0x180001812  mov     rsi, cs:WPP_GLOBAL_Control
0x180001819  cmp     ebx, 2
0x18000181c  jb      short loc_18000185A
0x18000181e  mov     rcx, [rbp+8]; String1
0x180001822  lea     rdx, aTriggerstarted; "TriggerStarted"
0x180001829  call    wcscmp_0
0x18000182e  test    eax, eax
0x180001830  jnz     short loc_18000185A
0x180001832  mov     edi, 1
0x180001837  cmp     rsi, r14
0x18000183a  jz      short loc_18000185A
0x18000183c  test    dword ptr [rsi+1Ch], 200h
0x180001843  jz      short loc_18000185A
0x180001845  mov     rcx, [rsi+10h]
0x180001849  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180001850  mov     edx, 10h
0x180001855  call    WPP_SF_
0x18000185a  mov     r8d, edi; int
0x18000185d  lea     rdx, ServiceName; "WpdBusEnum"
0x180001864  lea     rcx, ?_Service@@3VCService@@A; this
0x18000186b  call    ?Start@CService@@QEAAJPEBGH@Z; CService::Start(ushort const *,int)
0x180001870  mov     rax, cs:WPP_GLOBAL_Control
0x180001877  cmp     rax, r14
0x18000187a  jz      short loc_1800018A9
0x18000187c  test    dword ptr [rax+1Ch], 200h
0x180001883  jz      short loc_1800018A9
0x180001885  call    ?GetSystemTime@@YAKXZ; GetSystemTime(void)
0x18000188a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001891  lea     r8, WPP_b46f364b536c37ae0160bc29212cfef9_Traceguids
0x180001898  mov     edx, 11h
0x18000189d  mov     r9d, eax
0x1800018a0  mov     rcx, [rcx+10h]
0x1800018a4  call    WPP_SF_d
0x1800018a9  add     rsp, 20h
0x1800018ad  pop     r14
0x1800018af  pop     rdi
0x1800018b0  pop     rsi
0x1800018b1  pop     rbp
0x1800018b2  pop     rbx
0x1800018b3  retn
```
