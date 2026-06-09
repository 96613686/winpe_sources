# _Sleep

- ea: `0x18001e3cc`
- end: `0x18001e501`
- name: `_Sleep`
- size: `309`
- prototype: `__int64 __fastcall(DWORD dwTimeout)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006730`
- `0x180013c7c`
- `0x18001eae8`

## callees

- `0x18001e3cc`
- `0x180020710`
- `0x1800268b4`
- `0x1800269ac`
- `0x18002d6e8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001e4de`
- `KERNEL32!CloseHandle` at `0x18001e4de`
- `KERNEL32!CreateEventW` at `0x18001e446`
- `KERNEL32!CreateEventW` at `0x18001e446`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e4a7`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x18001e4a7`

## pseudocode

```c
__int64 __fastcall Sleep(DWORD dwTimeout)
{
  char *EventW; // rdi
  __int64 v3; // rdx
  unsigned int LastFailureAsHRESULT; // ebx
  __int64 v5; // r8
  unsigned int v7; // [rsp+30h] [rbp-40h] BYREF
  __int16 v8; // [rsp+34h] [rbp-3Ch]
  __int16 v9; // [rsp+36h] [rbp-3Ah]
  DWORD dwindex; // [rsp+88h] [rbp+18h] BYREF
  HANDLE pHandles; // [rsp+90h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x20000000) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids);
  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v7, "_Sleep", 4499, 1);
  dwindex = 0;
  pHandles = 0;
  EventW = (char *)CreateEventW(0, 0, 0, 0);
  if ( ((unsigned __int64)(EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v7 = 0;
    v8 = 4507;
    pHandles = EventW;
    LastFailureAsHRESULT = CoWaitForMultipleHandles(0, dwTimeout, 1u, &pHandles, &dwindex);
    if ( (int)(LastFailureAsHRESULT + 0x80000000) < 0 || LastFailureAsHRESULT == -2147417835 )
    {
      LastFailureAsHRESULT = 0;
      v8 = 4511;
    }
    else
    {
      v9 = 4511;
    }
    v7 = LastFailureAsHRESULT;
    goto LABEL_13;
  }
  LastFailureAsHRESULT = GetLastFailureAsHRESULT(EventW + 1);
  v7 = LastFailureAsHRESULT;
  v9 = 4507;
  if ( EventW && EventW != (char *)-1LL )
LABEL_13:
    CloseHandle(EventW);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v7, v3, v5);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18001e3cc  mov     [rsp-8+arg_0], rbx
0x18001e3d1  mov     [rsp-8+arg_18], rdi
0x18001e3d6  push    rbp
0x18001e3d7  mov     rbp, rsp
0x18001e3da  sub     rsp, 70h
0x18001e3de  mov     ebx, ecx
0x18001e3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3e7  lea     rax, WPP_GLOBAL_Control
0x18001e3ee  cmp     rcx, rax
0x18001e3f1  jz      short loc_18001E411
0x18001e3f3  test    dword ptr [rcx+1Ch], 20000000h
0x18001e3fa  jz      short loc_18001E411
0x18001e3fc  mov     rcx, [rcx+10h]
0x18001e400  lea     r8, WPP_c4639252eff5306510cbdeb3ef3cc4de_Traceguids
0x18001e407  mov     edx, 3Dh ; '='
0x18001e40c  call    WPP_SF_
0x18001e411  mov     r9d, 1; unsigned __int16
0x18001e417  lea     rdx, aSleep; "_Sleep"
0x18001e41e  mov     r8d, 1193h; unsigned __int16
0x18001e424  lea     rcx, [rbp+var_40]; this
0x18001e428  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18001e42d  xor     r9d, r9d; lpName
0x18001e430  mov     [rbp+dwindex], 0
0x18001e437  xor     r8d, r8d; bInitialState
0x18001e43a  mov     [rbp+pHandles], 0
0x18001e442  xor     edx, edx; bManualReset
0x18001e444  xor     ecx, ecx; lpEventAttributes
0x18001e446  call    cs:__imp_CreateEventW
0x18001e44c  mov     rdi, rax
0x18001e44f  lea     rcx, [rax+1]
0x18001e453  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18001e45a  jnz     short loc_18001E47C
0x18001e45c  call    GetLastFailureAsHRESULT
0x18001e461  mov     ebx, eax
0x18001e463  mov     [rbp+var_40], eax
0x18001e466  mov     eax, 119Bh
0x18001e46b  mov     [rbp+var_3A], ax
0x18001e46f  test    rdi, rdi
0x18001e472  jz      short loc_18001E4E4
0x18001e474  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18001e478  jz      short loc_18001E4E4
0x18001e47a  jmp     short loc_18001E4DB
0x18001e47c  mov     eax, 119Bh
0x18001e481  mov     [rbp+var_40], 0
0x18001e488  mov     [rbp+var_3C], ax
0x18001e48c  lea     r9, [rbp+pHandles]; pHandles
0x18001e490  lea     rax, [rbp+dwindex]
0x18001e494  mov     [rbp+pHandles], rdi
0x18001e498  mov     r8d, 1; cHandles
0x18001e49e  mov     [rsp+70h+lpdwindex], rax; lpdwindex
0x18001e4a3  mov     edx, ebx; dwTimeout
0x18001e4a5  xor     ecx, ecx; dwFlags
0x18001e4a7  call    cs:__imp_CoWaitForMultipleHandles
0x18001e4ad  mov     ecx, 80000000h
0x18001e4b2  mov     ebx, eax
0x18001e4b4  add     eax, ecx
0x18001e4b6  test    ecx, eax
0x18001e4b8  jnz     short loc_18001E4CD
0x18001e4ba  cmp     ebx, 80010115h
0x18001e4c0  jz      short loc_18001E4CD
0x18001e4c2  mov     eax, 119Fh
0x18001e4c7  mov     [rbp+var_3A], ax
0x18001e4cb  jmp     short loc_18001E4D8
0x18001e4cd  mov     eax, 119Fh
0x18001e4d2  xor     ebx, ebx
0x18001e4d4  mov     [rbp+var_3C], ax
0x18001e4d8  mov     [rbp+var_40], ebx
0x18001e4db  mov     rcx, rdi; hObject
0x18001e4de  call    cs:__imp_CloseHandle
0x18001e4e4  lea     rcx, [rbp+var_40]; this
0x18001e4e8  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18001e4ed  lea     r11, [rsp+70h+var_s0]
0x18001e4f2  mov     eax, ebx
0x18001e4f4  mov     rbx, [r11+10h]
0x18001e4f8  mov     rdi, [r11+28h]
0x18001e4fc  mov     rsp, r11
0x18001e4ff  pop     rbp
0x18001e500  retn
```
