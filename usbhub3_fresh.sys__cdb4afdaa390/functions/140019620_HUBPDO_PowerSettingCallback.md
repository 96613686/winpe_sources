# HUBPDO_PowerSettingCallback

- ea: `0x140019620`
- end: `0x1400198eb`
- name: `HUBPDO_PowerSettingCallback`
- size: `715`
- prototype: `POWER_SETTING_CALLBACK`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400024b8`
- `0x14000a53c`
- `0x140019620`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140019662`
- `ntoskrnl!RtlCompareMemory` at `0x1400196c9`
- `ntoskrnl!RtlCompareMemory` at `0x1400196eb`
- `ntoskrnl!RtlCompareMemory` at `0x14001970d`
- `ntoskrnl!RtlCompareMemory` at `0x14001972f`
- `ntoskrnl!RtlCompareMemory` at `0x140019751`
- `ntoskrnl!RtlCompareMemory` at `0x140019773`
- `ntoskrnl!RtlCompareMemory` at `0x140019791`
- `ntoskrnl!RtlCompareMemory` at `0x1400197af`
- `ntoskrnl!RtlCompareMemory` at `0x1400198a8`
- `ntoskrnl!RtlCompareMemory` at `0x140019662`
- `ntoskrnl!RtlCompareMemory` at `0x1400196c9`
- `ntoskrnl!RtlCompareMemory` at `0x1400196eb`
- `ntoskrnl!RtlCompareMemory` at `0x14001970d`
- `ntoskrnl!RtlCompareMemory` at `0x14001972f`
- `ntoskrnl!RtlCompareMemory` at `0x140019751`
- `ntoskrnl!RtlCompareMemory` at `0x140019773`
- `ntoskrnl!RtlCompareMemory` at `0x140019791`
- `ntoskrnl!RtlCompareMemory` at `0x1400197af`
- `ntoskrnl!RtlCompareMemory` at `0x1400198a8`

## pseudocode

```c
__int64 __fastcall HUBPDO_PowerSettingCallback(LPCGUID SettingGuid, int *Value, ULONG ValueLength, _DWORD *Context)
{
  _DWORD *v4; // r14
  int v9; // edx
  int v10; // eax
  int v11; // eax
  char v12; // al
  int v13; // eax
  char v14; // cl
  char v15; // al
  unsigned int v16; // ebx
  int Source1; // [rsp+78h] [rbp+48h] BYREF

  v4 = Context + 557;
  Source1 = Context[557];
  if ( RtlCompareMemory(SettingGuid, &GUID_POWER_USB_3_LINK_POWER_MANAGEMENT_POLICY, 0x10u) != 16 )
  {
    if ( RtlCompareMemory(SettingGuid, &GUID_POWER_USB_U1_ENABLE_FOR_DEVICES, 0x10u) == 16
      || RtlCompareMemory(SettingGuid, &GUID_POWER_USB_U1_ENABLE_FOR_HUBS, 0x10u) == 16 )
    {
      if ( ValueLength < 4 )
        goto LABEL_37;
      v14 = *Value != 0;
      v15 = Source1 & 0xFE;
    }
    else
    {
      if ( RtlCompareMemory(SettingGuid, &GUID_POWER_USB_U2_ENABLE_FOR_DEVICES, 0x10u) != 16
        && RtlCompareMemory(SettingGuid, &GUID_POWER_USB_U2_ENABLE_FOR_HUBS, 0x10u) != 16 )
      {
        if ( RtlCompareMemory(SettingGuid, &GUID_POWER_USB_U1_TIMEOUT_FOR_DEVICES, 0x10u) == 16
          || RtlCompareMemory(SettingGuid, &GUID_POWER_USB_U1_TIMEOUT_FOR_HUBS, 0x10u) == 16 )
        {
          if ( ValueLength < 4 )
            goto LABEL_37;
          v13 = *Value;
          if ( *Value )
          {
            if ( v13 != 1 )
            {
              if ( v13 == 2 )
                LOBYTE(Source1) = Source1 & 0xEB;
              goto LABEL_41;
            }
            v12 = Source1 & 0xEB | 4;
LABEL_24:
            LOBYTE(Source1) = v12;
            goto LABEL_41;
          }
          LOBYTE(Source1) = Source1 | 0x14;
        }
        else if ( RtlCompareMemory(SettingGuid, &GUID_POWER_USB_U2_TIMEOUT_FOR_DEVICES, 0x10u) == 16
               || RtlCompareMemory(SettingGuid, &GUID_POWER_USB_U2_TIMEOUT_FOR_HUBS, 0x10u) == 16 )
        {
          if ( ValueLength < 4 )
            goto LABEL_37;
          v11 = *Value;
          if ( !*Value )
          {
            LOBYTE(Source1) = Source1 | 0x28;
            goto LABEL_41;
          }
          if ( v11 != 1 )
          {
            if ( v11 == 2 )
              LOBYTE(Source1) = Source1 & 0xD7;
            goto LABEL_41;
          }
          v12 = Source1 & 0xD7 | 8;
          goto LABEL_24;
        }
LABEL_41:
        v16 = 0;
        if ( RtlCompareMemory(&Source1, v4, 4u) != 4 )
        {
          *v4 = Source1;
          HUBSM_AddEvent((__int64)(Context + 128), 4055);
        }
        return v16;
      }
      if ( ValueLength < 4 )
        goto LABEL_37;
      v14 = *Value != 0 ? 2 : 0;
      v15 = Source1 & 0xFD;
    }
    LOBYTE(Source1) = v15 | v14;
    goto LABEL_41;
  }
  v10 = *Value;
  if ( (unsigned int)*Value <= 3 )
  {
    if ( v10 )
    {
      LOBYTE(Source1) = Source1 | 0x3F;
      switch ( v10 )
      {
        case 1:
          LOBYTE(Source1) = 127;
          break;
        case 2:
          LOBYTE(Source1) = 63;
          break;
        case 3:
          LOBYTE(Source1) = -65;
          break;
      }
    }
    else
    {
      Source1 = 0;
    }
    goto LABEL_41;
  }
LABEL_37:
  v16 = -1073741811;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_d(
      *(_QWORD *)(*((_QWORD *)Context + 1) + 1432LL),
      v9,
      2,
      136,
      (__int64)WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids,
      -1073741811);
  }
  return v16;
}

```

## disassembly

```asm
0x140019620  mov     [rsp-28h+arg_0], rbx
0x140019625  mov     [rsp-28h+arg_8], rsi
0x14001962a  push    rbp
0x14001962b  push    rdi
0x14001962c  push    r12
0x14001962e  push    r14
0x140019630  push    r15
0x140019632  mov     rbp, rsp
0x140019635  sub     rsp, 30h
0x140019639  lea     r14, [r9+8B4h]
0x140019640  mov     esi, r8d
0x140019643  mov     eax, [r14]
0x140019646  mov     rdi, rdx
0x140019649  mov     r12d, 10h
0x14001964f  mov     [rbp+Source1], eax
0x140019652  mov     r8d, r12d; Length
0x140019655  lea     rdx, GUID_POWER_USB_3_LINK_POWER_MANAGEMENT_POLICY; Source2
0x14001965c  mov     r15, r9
0x14001965f  mov     rbx, rcx
0x140019662  call    cs:__imp_RtlCompareMemory
0x140019669  nop     dword ptr [rax+rax+00h]
0x14001966e  cmp     rax, r12
0x140019671  jnz     short loc_1400196BC
0x140019673  mov     eax, [rdi]
0x140019675  cmp     eax, 3
0x140019678  ja      loc_140019845
0x14001967e  test    eax, eax
0x140019680  jnz     short loc_14001968A
0x140019682  mov     [rbp+Source1], eax
0x140019685  jmp     loc_14001989B
0x14001968a  or      byte ptr [rbp+Source1], 3Fh
0x14001968e  cmp     eax, 1
0x140019691  jnz     short loc_14001969C
0x140019693  mov     byte ptr [rbp+Source1], 7Fh
0x140019697  jmp     loc_14001989B
0x14001969c  cmp     eax, 2
0x14001969f  jnz     short loc_1400196AA
0x1400196a1  mov     byte ptr [rbp+Source1], 3Fh ; '?'
0x1400196a5  jmp     loc_14001989B
0x1400196aa  cmp     eax, 3
0x1400196ad  jnz     loc_14001989B
0x1400196b3  mov     byte ptr [rbp+Source1], 0BFh
0x1400196b7  jmp     loc_14001989B
0x1400196bc  mov     r8, r12; Length
0x1400196bf  lea     rdx, GUID_POWER_USB_U1_ENABLE_FOR_DEVICES; Source2
0x1400196c6  mov     rcx, rbx; Source1
0x1400196c9  call    cs:__imp_RtlCompareMemory
0x1400196d0  nop     dword ptr [rax+rax+00h]
0x1400196d5  cmp     rax, r12
0x1400196d8  jz      loc_140019840
0x1400196de  mov     r8, r12; Length
0x1400196e1  lea     rdx, GUID_POWER_USB_U1_ENABLE_FOR_HUBS; Source2
0x1400196e8  mov     rcx, rbx; Source1
0x1400196eb  call    cs:__imp_RtlCompareMemory
0x1400196f2  nop     dword ptr [rax+rax+00h]
0x1400196f7  cmp     rax, r12
0x1400196fa  jz      loc_140019840
0x140019700  mov     r8, r12; Length
0x140019703  lea     rdx, GUID_POWER_USB_U2_ENABLE_FOR_DEVICES; Source2
0x14001970a  mov     rcx, rbx; Source1
0x14001970d  call    cs:__imp_RtlCompareMemory
0x140019714  nop     dword ptr [rax+rax+00h]
0x140019719  cmp     rax, r12
0x14001971c  jz      loc_14001982B
0x140019722  mov     r8, r12; Length
0x140019725  lea     rdx, GUID_POWER_USB_U2_ENABLE_FOR_HUBS; Source2
0x14001972c  mov     rcx, rbx; Source1
0x14001972f  call    cs:__imp_RtlCompareMemory
0x140019736  nop     dword ptr [rax+rax+00h]
0x14001973b  cmp     rax, r12
0x14001973e  jz      loc_14001982B
0x140019744  mov     r8, r12; Length
0x140019747  lea     rdx, GUID_POWER_USB_U1_TIMEOUT_FOR_DEVICES; Source2
0x14001974e  mov     rcx, rbx; Source1
0x140019751  call    cs:__imp_RtlCompareMemory
0x140019758  nop     dword ptr [rax+rax+00h]
0x14001975d  cmp     rax, r12
0x140019760  jz      loc_1400197FE
0x140019766  mov     r8, r12; Length
0x140019769  lea     rdx, GUID_POWER_USB_U1_TIMEOUT_FOR_HUBS; Source2
0x140019770  mov     rcx, rbx; Source1
0x140019773  call    cs:__imp_RtlCompareMemory
0x14001977a  nop     dword ptr [rax+rax+00h]
0x14001977f  cmp     rax, r12
0x140019782  jz      short loc_1400197FE
0x140019784  mov     r8, r12; Length
0x140019787  lea     rdx, GUID_POWER_USB_U2_TIMEOUT_FOR_DEVICES; Source2
0x14001978e  mov     rcx, rbx; Source1
0x140019791  call    cs:__imp_RtlCompareMemory
0x140019798  nop     dword ptr [rax+rax+00h]
0x14001979d  cmp     rax, r12
0x1400197a0  jz      short loc_1400197C4
0x1400197a2  mov     r8, r12; Length
0x1400197a5  lea     rdx, GUID_POWER_USB_U2_TIMEOUT_FOR_HUBS; Source2
0x1400197ac  mov     rcx, rbx; Source1
0x1400197af  call    cs:__imp_RtlCompareMemory
0x1400197b6  nop     dword ptr [rax+rax+00h]
0x1400197bb  cmp     rax, r12
0x1400197be  jnz     loc_14001989B
0x1400197c4  cmp     esi, 4
0x1400197c7  jb      short loc_140019845
0x1400197c9  mov     eax, [rdi]
0x1400197cb  test    eax, eax
0x1400197cd  jnz     short loc_1400197D8
0x1400197cf  or      byte ptr [rbp+Source1], 28h
0x1400197d3  jmp     loc_14001989B
0x1400197d8  cmp     eax, 1
0x1400197db  jnz     short loc_1400197EC
0x1400197dd  mov     al, byte ptr [rbp+Source1]
0x1400197e0  and     al, 0DFh
0x1400197e2  or      al, 8
0x1400197e4  mov     byte ptr [rbp+Source1], al
0x1400197e7  jmp     loc_14001989B
0x1400197ec  cmp     eax, 2
0x1400197ef  jnz     loc_14001989B
0x1400197f5  and     byte ptr [rbp+Source1], 0D7h
0x1400197f9  jmp     loc_14001989B
0x1400197fe  cmp     esi, 4
0x140019801  jb      short loc_140019845
0x140019803  mov     eax, [rdi]
0x140019805  test    eax, eax
0x140019807  jnz     short loc_140019812
0x140019809  or      byte ptr [rbp+Source1], 14h
0x14001980d  jmp     loc_14001989B
0x140019812  cmp     eax, 1
0x140019815  jnz     short loc_140019820
0x140019817  mov     al, byte ptr [rbp+Source1]
0x14001981a  and     al, 0EFh
0x14001981c  or      al, 4
0x14001981e  jmp     short loc_1400197E4
0x140019820  cmp     eax, 2
0x140019823  jnz     short loc_14001989B
0x140019825  and     byte ptr [rbp+Source1], 0EBh
0x140019829  jmp     short loc_14001989B
0x14001982b  cmp     esi, 4
0x14001982e  jb      short loc_140019845
0x140019830  mov     eax, [rdi]
0x140019832  neg     eax
0x140019834  mov     al, byte ptr [rbp+Source1]
0x140019837  sbb     cl, cl
0x140019839  and     cl, 2
0x14001983c  and     al, 0FDh
0x14001983e  jmp     short loc_140019896
0x140019840  cmp     esi, 4
0x140019843  jnb     short loc_14001988B
0x140019845  mov     ebx, 0C000000Dh
0x14001984a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140019851  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140019858  jz      short loc_1400198D1
0x14001985a  mov     rcx, [r15+8]
0x14001985e  lea     rax, WPP_8beb7df92ba934db5f6899fb45b5938a_Traceguids
0x140019865  mov     r8d, 2
0x14001986b  mov     [rsp+30h+var_8], ebx
0x14001986f  mov     r9d, 88h
0x140019875  mov     [rsp+30h+var_10], rax
0x14001987a  mov     dl, r8b
0x14001987d  mov     rcx, [rcx+598h]
0x140019884  call    WPP_RECORDER_SF_d
0x140019889  jmp     short loc_1400198D1
0x14001988b  cmp     dword ptr [rdi], 0
0x14001988e  mov     al, byte ptr [rbp+Source1]
0x140019891  setnz   cl
0x140019894  and     al, 0FEh
0x140019896  or      cl, al
0x140019898  mov     byte ptr [rbp+Source1], cl
0x14001989b  xor     ebx, ebx
0x14001989d  lea     rcx, [rbp+Source1]; Source1
0x1400198a1  mov     rdx, r14; Source2
0x1400198a4  lea     r8d, [rbx+4]; Length
0x1400198a8  call    cs:__imp_RtlCompareMemory
0x1400198af  nop     dword ptr [rax+rax+00h]
0x1400198b4  cmp     rax, 4
0x1400198b8  jz      short loc_1400198D1
0x1400198ba  mov     ecx, [rbp+Source1]
0x1400198bd  mov     edx, 0FD7h
0x1400198c2  mov     [r14], ecx
0x1400198c5  lea     rcx, [r15+200h]
0x1400198cc  call    HUBSM_AddEvent
0x1400198d1  mov     rsi, [rsp+30h+arg_8]
0x1400198d6  mov     eax, ebx
0x1400198d8  mov     rbx, [rsp+30h+arg_0]
0x1400198dd  add     rsp, 30h
0x1400198e1  pop     r15
0x1400198e3  pop     r14
0x1400198e5  pop     r12
0x1400198e7  pop     rdi
0x1400198e8  pop     rbp
0x1400198e9  retn
```
