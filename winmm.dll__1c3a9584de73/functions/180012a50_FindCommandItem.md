# FindCommandItem

- ea: `0x180012a50`
- end: `0x180012c44`
- name: `FindCommandItem`
- size: `500`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011610`
- `0x180013328`

## callees

- `0x18000a02c`
- `0x18000b1f8`
- `0x18000b6d4`
- `0x1800127ac`
- `0x180012a50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012b43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012b43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012b95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012bc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012bf8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012b95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012bc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012bf8`

## pseudocode

```c
const WCHAR *__fastcall FindCommandItem(unsigned int a1, __int64 a2, const WCHAR *a3, _DWORD *a4, unsigned int *a5)
{
  __int64 v5; // rdi
  __int64 v9; // rbp
  unsigned int v10; // ebx
  const WCHAR *CommandInTable; // rdi

  v5 = a1;
  if ( (unsigned __int64)a3 < 0x10000 )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids,
        (unsigned __int16)a3);
    }
  }
  else
  {
    if ( !*a3 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0 )
      {
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids);
      }
      return 0;
    }
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids, a3);
    }
  }
  if ( (unsigned int)(v5 - 1) > 0xFFFFFFFD )
    goto LABEL_31;
  EnterCriticalSection(&mciCritSec);
  if ( (unsigned int)v5 >= MCI_wNextDeviceID
    || !*((_QWORD *)MCI_lpDeviceList + v5)
    || (_mm_lfence(), (v9 = *((_QWORD *)MCI_lpDeviceList + v5)) == 0) )
  {
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids);
    }
    LeaveCriticalSection(&mciCritSec);
    return 0;
  }
  v10 = *(_DWORD *)(v9 + 64);
  if ( v10 == -1 || (CommandInTable = FindCommandInTable(v10, a3, a4)) == 0 )
  {
    v10 = *(_DWORD *)(v9 + 60);
    if ( v10 == -1 || (CommandInTable = FindCommandInTable(v10, a3, a4)) == 0 )
    {
      LeaveCriticalSection(&mciCritSec);
LABEL_31:
      v10 = 0;
      CommandInTable = FindCommandInTable(0, a3, a4);
      if ( !CommandInTable )
        v10 = -1;
      goto LABEL_33;
    }
  }
  LeaveCriticalSection(&mciCritSec);
LABEL_33:
  if ( a5 )
    *a5 = v10;
  return CommandInTable;
}

```

## disassembly

```asm
0x180012a50  push    rbx
0x180012a52  push    rbp
0x180012a53  push    rsi
0x180012a54  push    rdi
0x180012a55  push    r12
0x180012a57  push    r13
0x180012a59  push    r14
0x180012a5b  push    r15
0x180012a5d  sub     rsp, 28h
0x180012a61  xor     r12d, r12d
0x180012a64  mov     edi, ecx
0x180012a66  mov     r14, r9
0x180012a69  mov     rsi, r8
0x180012a6c  mov     r13d, 400000h
0x180012a72  cmp     r8, 10000h
0x180012a79  jb      short loc_180012AF5
0x180012a7b  cmp     [r8], r12w
0x180012a7f  jnz     short loc_180012ABC
0x180012a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a88  lea     rbx, WPP_GLOBAL_Control
0x180012a8f  cmp     rcx, rbx
0x180012a92  jz      short loc_180012AB5
0x180012a94  test    [rcx+1Ch], r13d
0x180012a98  jz      short loc_180012AB5
0x180012a9a  cmp     byte ptr [rcx+19h], 1
0x180012a9e  jb      short loc_180012AB5
0x180012aa0  mov     rcx, [rcx+10h]
0x180012aa4  lea     edx, [r12+29h]
0x180012aa9  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180012ab0  call    WPP_SF_
0x180012ab5  xor     eax, eax
0x180012ab7  jmp     loc_180012C33
0x180012abc  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ac3  lea     rbx, WPP_GLOBAL_Control
0x180012aca  cmp     rcx, rbx
0x180012acd  jz      short loc_180012B2D
0x180012acf  test    [rcx+1Ch], r13d
0x180012ad3  jz      short loc_180012B2D
0x180012ad5  cmp     byte ptr [rcx+19h], 3
0x180012ad9  jb      short loc_180012B2D
0x180012adb  mov     rcx, [rcx+10h]
0x180012adf  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180012ae6  mov     edx, 2Ah ; '*'
0x180012aeb  mov     r9, rsi
0x180012aee  call    WPP_SF_S
0x180012af3  jmp     short loc_180012B2D
0x180012af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180012afc  lea     rbx, WPP_GLOBAL_Control
0x180012b03  cmp     rcx, rbx
0x180012b06  jz      short loc_180012B2D
0x180012b08  test    [rcx+1Ch], r13d
0x180012b0c  jz      short loc_180012B2D
0x180012b0e  cmp     byte ptr [rcx+19h], 3
0x180012b12  jb      short loc_180012B2D
0x180012b14  mov     rcx, [rcx+10h]
0x180012b18  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180012b1f  movzx   r9d, si
0x180012b23  mov     edx, 2Bh ; '+'
0x180012b28  call    WPP_SF_d
0x180012b2d  lea     eax, [rdi-1]
0x180012b30  cmp     eax, 0FFFFFFFDh
0x180012b33  ja      loc_180012C03
0x180012b39  lea     r15, mciCritSec
0x180012b40  mov     rcx, r15; lpCriticalSection
0x180012b43  call    cs:__imp_EnterCriticalSection
0x180012b49  cmp     edi, cs:MCI_wNextDeviceID
0x180012b4f  jnb     short loc_180012BC8
0x180012b51  mov     rax, cs:MCI_lpDeviceList
0x180012b58  cmp     [rax+rdi*8], r12
0x180012b5c  jz      short loc_180012BC8
0x180012b5e  lfence
0x180012b61  mov     rax, cs:MCI_lpDeviceList
0x180012b68  mov     rbp, [rax+rdi*8]
0x180012b6c  test    rbp, rbp
0x180012b6f  jz      short loc_180012BC8
0x180012b71  mov     ebx, [rbp+40h]
0x180012b74  or      r13d, 0FFFFFFFFh
0x180012b78  cmp     ebx, r13d
0x180012b7b  jz      short loc_180012BA0
0x180012b7d  mov     r8, r14
0x180012b80  mov     rdx, rsi
0x180012b83  mov     ecx, ebx
0x180012b85  call    FindCommandInTable
0x180012b8a  mov     rdi, rax
0x180012b8d  test    rax, rax
0x180012b90  jz      short loc_180012BA0
0x180012b92  mov     rcx, r15; lpCriticalSection
0x180012b95  call    cs:__imp_LeaveCriticalSection
0x180012b9b  jmp     loc_180012C21
0x180012ba0  mov     ebx, [rbp+3Ch]
0x180012ba3  cmp     ebx, r13d
0x180012ba6  jz      short loc_180012BBD
0x180012ba8  mov     r8, r14
0x180012bab  mov     rdx, rsi
0x180012bae  mov     ecx, ebx
0x180012bb0  call    FindCommandInTable
0x180012bb5  mov     rdi, rax
0x180012bb8  test    rax, rax
0x180012bbb  jnz     short loc_180012B92
0x180012bbd  mov     rcx, r15; lpCriticalSection
0x180012bc0  call    cs:__imp_LeaveCriticalSection
0x180012bc6  jmp     short loc_180012C07
0x180012bc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180012bcf  cmp     rcx, rbx
0x180012bd2  jz      short loc_180012BF5
0x180012bd4  test    [rcx+1Ch], r13d
0x180012bd8  jz      short loc_180012BF5
0x180012bda  cmp     byte ptr [rcx+19h], 1
0x180012bde  jb      short loc_180012BF5
0x180012be0  mov     rcx, [rcx+10h]
0x180012be4  lea     r8, WPP_353f1923cdf435773b940fd9bc246a0f_Traceguids
0x180012beb  mov     edx, 2Ch ; ','
0x180012bf0  call    WPP_SF_
0x180012bf5  mov     rcx, r15; lpCriticalSection
0x180012bf8  call    cs:__imp_LeaveCriticalSection
0x180012bfe  jmp     loc_180012AB5
0x180012c03  or      r13d, 0FFFFFFFFh
0x180012c07  mov     r8, r14
0x180012c0a  mov     rdx, rsi
0x180012c0d  xor     ecx, ecx
0x180012c0f  mov     ebx, r12d
0x180012c12  call    FindCommandInTable
0x180012c17  test    rax, rax
0x180012c1a  mov     rdi, rax
0x180012c1d  cmovz   ebx, r13d
0x180012c21  mov     rax, [rsp+68h+arg_20]
0x180012c29  test    rax, rax
0x180012c2c  jz      short loc_180012C30
0x180012c2e  mov     [rax], ebx
0x180012c30  mov     rax, rdi
0x180012c33  add     rsp, 28h
0x180012c37  pop     r15
0x180012c39  pop     r14
0x180012c3b  pop     r13
0x180012c3d  pop     r12
0x180012c3f  pop     rdi
0x180012c40  pop     rsi
0x180012c41  pop     rbp
0x180012c42  pop     rbx
0x180012c43  retn
```
