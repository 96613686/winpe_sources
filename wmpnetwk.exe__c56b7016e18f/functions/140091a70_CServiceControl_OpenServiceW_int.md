# CServiceControl::OpenServiceW(int)

- ea: `0x140091a70`
- end: `0x140091ba1`
- name: `?OpenServiceW@CServiceControl@@AEAAHH@Z`
- size: `305`
- prototype: `__int64 __fastcall(CServiceControl *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140091ba8`
- `0x140091d60`

## callees

- `0x14003f17c`
- `0x140047798`
- `0x140091984`
- `0x140091a70`

## import_xrefs

- `ADVAPI32!OpenServiceW` at `0x140091b20`
- `ADVAPI32!OpenServiceW` at `0x140091b20`
- `KERNEL32!GetLastError` at `0x140091b31`
- `KERNEL32!GetLastError` at `0x140091b31`

## pseudocode

```c
__int64 __fastcall CServiceControl::OpenServiceW(CServiceControl *this, int a2)
{
  PVOID *v4; // rcx
  unsigned int v5; // ebx
  unsigned int v6; // eax
  DWORD v7; // r8d
  SC_HANDLE v8; // rax
  DWORD LastError; // eax

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_cb23d491edf93b904e2862226171c496_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = 1;
  if ( *((_QWORD *)this + 2) )
    goto LABEL_18;
  v6 = CServiceControl::OpenServiceManager(this);
  v5 = v6;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_cb23d491edf93b904e2862226171c496_Traceguids, v6);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 != 1 )
    goto LABEL_18;
  v7 = 311;
  if ( a2 != 1 )
    v7 = 277;
  v8 = OpenServiceW(*((SC_HANDLE *)this + 1), *(LPCWSTR *)this, v7);
  *((_QWORD *)this + 2) = v8;
  if ( v8 )
    goto LABEL_17;
  v5 = 0;
  LastError = GetLastError();
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_cb23d491edf93b904e2862226171c496_Traceguids, LastError);
LABEL_17:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_18:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_d(v4[2], 58, WPP_cb23d491edf93b904e2862226171c496_Traceguids, v5);
  return v5;
}

```

## disassembly

```asm
0x140091a70  push    rbx
0x140091a72  push    rsi
0x140091a73  push    rdi
0x140091a74  push    r14
0x140091a76  sub     rsp, 28h
0x140091a7a  mov     esi, edx
0x140091a7c  mov     rdi, rcx
0x140091a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140091a86  lea     r14, WPP_GLOBAL_Control
0x140091a8d  cmp     rcx, r14
0x140091a90  jz      short loc_140091AB4
0x140091a92  test    byte ptr [rcx+1Ch], 1
0x140091a96  jz      short loc_140091AB4
0x140091a98  mov     rcx, [rcx+10h]
0x140091a9c  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091aa3  mov     edx, 37h ; '7'
0x140091aa8  call    WPP_SF_
0x140091aad  mov     rcx, cs:WPP_GLOBAL_Control
0x140091ab4  cmp     qword ptr [rdi+10h], 0
0x140091ab9  mov     ebx, 1
0x140091abe  jnz     loc_140091B6C
0x140091ac4  mov     rcx, rdi; this
0x140091ac7  call    ?OpenServiceManager@CServiceControl@@AEAAHXZ; CServiceControl::OpenServiceManager(void)
0x140091acc  mov     ebx, eax
0x140091ace  mov     rcx, cs:WPP_GLOBAL_Control
0x140091ad5  cmp     rcx, r14
0x140091ad8  jz      short loc_140091B05
0x140091ada  test    byte ptr [rcx+1Ch], 2
0x140091ade  jz      short loc_140091B05
0x140091ae0  cmp     byte ptr [rcx+19h], 4
0x140091ae4  jb      short loc_140091B05
0x140091ae6  mov     rcx, [rcx+10h]
0x140091aea  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091af1  mov     edx, 38h ; '8'
0x140091af6  mov     r9d, eax
0x140091af9  call    WPP_SF_d
0x140091afe  mov     rcx, cs:WPP_GLOBAL_Control
0x140091b05  cmp     ebx, 1
0x140091b08  jnz     short loc_140091B6C
0x140091b0a  mov     rdx, [rdi]; lpServiceName
0x140091b0d  mov     eax, 115h
0x140091b12  mov     rcx, [rdi+8]; hSCManager
0x140091b16  cmp     esi, ebx
0x140091b18  lea     r8d, [rax+22h]
0x140091b1c  cmovnz  r8d, eax; dwDesiredAccess
0x140091b20  call    cs:__imp_OpenServiceW
0x140091b26  mov     [rdi+10h], rax
0x140091b2a  test    rax, rax
0x140091b2d  jnz     short loc_140091B65
0x140091b2f  xor     ebx, ebx
0x140091b31  call    cs:__imp_GetLastError
0x140091b37  mov     rcx, cs:WPP_GLOBAL_Control
0x140091b3e  cmp     rcx, r14
0x140091b41  jz      short loc_140091B95
0x140091b43  test    byte ptr [rcx+1Ch], 2
0x140091b47  jz      short loc_140091B6C
0x140091b49  cmp     byte ptr [rcx+19h], 4
0x140091b4d  jb      short loc_140091B6C
0x140091b4f  mov     rcx, [rcx+10h]
0x140091b53  lea     edx, [rbx+39h]
0x140091b56  mov     r9d, eax
0x140091b59  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091b60  call    WPP_SF_d
0x140091b65  mov     rcx, cs:WPP_GLOBAL_Control
0x140091b6c  cmp     rcx, r14
0x140091b6f  jz      short loc_140091B95
0x140091b71  test    byte ptr [rcx+1Ch], 1
0x140091b75  jz      short loc_140091B95
0x140091b77  cmp     byte ptr [rcx+19h], 5
0x140091b7b  jb      short loc_140091B95
0x140091b7d  mov     rcx, [rcx+10h]
0x140091b81  lea     r8, WPP_cb23d491edf93b904e2862226171c496_Traceguids
0x140091b88  mov     edx, 3Ah ; ':'
0x140091b8d  mov     r9d, ebx
0x140091b90  call    WPP_SF_d
0x140091b95  mov     eax, ebx
0x140091b97  add     rsp, 28h
0x140091b9b  pop     r14
0x140091b9d  pop     rdi
0x140091b9e  pop     rsi
0x140091b9f  pop     rbx
0x140091ba0  retn
```
