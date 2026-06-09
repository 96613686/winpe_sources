# HashCompute::ComputeHash(uchar * const,ulong,uchar *,ulong *)

- ea: `0x180038120`
- end: `0x180038317`
- name: `?ComputeHash@HashCompute@@QEAAKQEAEKPEAEPEAK@Z`
- size: `503`
- prototype: `__int64 __fastcall(HashCompute *this, unsigned __int8 *const, ULONG, unsigned __int8 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180038000`
- `0x18006eae0`

## callees

- `0x180038120`
- `0x180054084`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800382d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800382f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800382d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800382f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038196`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038196`
- `ntdll!RtlNtStatusToDosError` at `0x1800382b2`
- `ntdll!RtlNtStatusToDosError` at `0x1800382b2`
- `bcrypt!BCryptDestroyHash` at `0x1800382c4`
- `bcrypt!BCryptDestroyHash` at `0x1800382e0`
- `bcrypt!BCryptDestroyHash` at `0x1800382c4`
- `bcrypt!BCryptDestroyHash` at `0x1800382e0`
- `bcrypt!BCryptHashData` at `0x180038223`
- `bcrypt!BCryptHashData` at `0x180038223`
- `bcrypt!BCryptFinishHash` at `0x180038268`
- `bcrypt!BCryptFinishHash` at `0x180038268`
- `bcrypt!BCryptCreateHash` at `0x1800381cf`
- `bcrypt!BCryptCreateHash` at `0x1800381cf`

## pseudocode

```c
__int64 __fastcall HashCompute::ComputeHash(
        HashCompute *this,
        unsigned __int8 *const a2,
        ULONG a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  ULONG *v9; // rbx
  int v10; // edi
  _QWORD *v11; // r10
  __int64 v12; // rdx
  ULONG v13; // ebx
  BCRYPT_HASH_HANDLE phHash; // [rsp+60h] [rbp+8h] BYREF

  phHash = 0;
  if ( !_InterlockedCompareExchange(&dword_1800BC660, 0, 0) )
    return 31;
  if ( !a2 )
    return 87;
  if ( !a4 )
    return 87;
  v9 = a5;
  if ( !a5 || *a5 < *(_DWORD *)&dword_1800BC64C )
    return 87;
  EnterCriticalSection(&CriticalSection);
  v10 = BCryptCreateHash(hAlgorithm, &phHash, pbHashObject, dwBytes, 0, 0, 0);
  if ( v10 >= 0 )
  {
    v10 = BCryptHashData(phHash, a2, a3, 0);
    if ( v10 >= 0 )
    {
      v10 = BCryptFinishHash(phHash, a4, *v9, 0);
      if ( v10 >= 0 )
      {
        BCryptDestroyHash(phHash);
        *v9 = *(_DWORD *)&dword_1800BC64C;
        LeaveCriticalSection(&CriticalSection);
        return 0;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_23;
      }
      v12 = 16;
      goto LABEL_22;
    }
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 15;
      goto LABEL_22;
    }
  }
  else
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x40000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 14;
LABEL_22:
      WPP_SF_d(v11[2], v12, WPP_2b8d55565e60367fc767d22ca087624d_Traceguids, (unsigned int)v10);
    }
  }
LABEL_23:
  v13 = RtlNtStatusToDosError(v10);
  if ( phHash )
    BCryptDestroyHash(phHash);
  LeaveCriticalSection(&CriticalSection);
  return v13;
}

```

## disassembly

```asm
0x180038120  mov     rax, rsp
0x180038123  mov     [rax+10h], rbx
0x180038127  mov     [rax+18h], rbp
0x18003812b  mov     [rax+8], rcx
0x18003812f  push    rsi
0x180038130  push    rdi
0x180038131  push    r14
0x180038133  sub     rsp, 40h
0x180038137  xor     ecx, ecx
0x180038139  mov     qword ptr [rax+8], 0
0x180038141  xor     eax, eax
0x180038143  mov     rsi, r9
0x180038146  mov     r14d, r8d
0x180038149  mov     rbp, rdx
0x18003814c  lock cmpxchg cs:dword_1800BC660, ecx
0x180038154  jnz     short loc_18003815E
0x180038156  lea     eax, [rcx+1Fh]
0x180038159  jmp     loc_180038304
0x18003815e  test    rbp, rbp
0x180038161  jz      loc_1800382FF
0x180038167  test    rsi, rsi
0x18003816a  jz      loc_1800382FF
0x180038170  mov     rbx, [rsp+58h+arg_20]
0x180038178  test    rbx, rbx
0x18003817b  jz      loc_1800382FF
0x180038181  mov     eax, cs:dword_1800BC64C
0x180038187  cmp     [rbx], eax
0x180038189  jb      loc_1800382FF
0x18003818f  lea     rcx, CriticalSection; lpCriticalSection
0x180038196  call    cs:__imp_EnterCriticalSection
0x18003819c  mov     r9d, cs:dwBytes; cbHashObject
0x1800381a3  lea     rdx, [rsp+58h+phHash]; phHash
0x1800381a8  mov     r8, cs:pbHashObject; pbHashObject
0x1800381af  mov     rcx, cs:hAlgorithm; hAlgorithm
0x1800381b6  mov     [rsp+58h+dwFlags], 0; dwFlags
0x1800381be  mov     [rsp+58h+cbSecret], 0; cbSecret
0x1800381c6  mov     [rsp+58h+pbSecret], 0; pbSecret
0x1800381cf  call    cs:__imp_BCryptCreateHash
0x1800381d5  mov     edi, eax
0x1800381d7  test    eax, eax
0x1800381d9  jns     short loc_180038215
0x1800381db  mov     r10, cs:WPP_GLOBAL_Control
0x1800381e2  lea     rcx, WPP_GLOBAL_Control
0x1800381e9  cmp     r10, rcx
0x1800381ec  jz      loc_1800382B0
0x1800381f2  test    dword ptr [r10+1Ch], 40000h
0x1800381fa  jz      loc_1800382B0
0x180038200  cmp     byte ptr [r10+19h], 2
0x180038205  jb      loc_1800382B0
0x18003820b  mov     edx, 0Eh
0x180038210  jmp     loc_18003829D
0x180038215  mov     rcx, [rsp+58h+phHash]; hHash
0x18003821a  xor     r9d, r9d; dwFlags
0x18003821d  mov     r8d, r14d; cbInput
0x180038220  mov     rdx, rbp; pbInput
0x180038223  call    cs:__imp_BCryptHashData
0x180038229  mov     edi, eax
0x18003822b  test    eax, eax
0x18003822d  jns     short loc_18003825A
0x18003822f  mov     r10, cs:WPP_GLOBAL_Control
0x180038236  lea     rcx, WPP_GLOBAL_Control
0x18003823d  cmp     r10, rcx
0x180038240  jz      short loc_1800382B0
0x180038242  test    dword ptr [r10+1Ch], 40000h
0x18003824a  jz      short loc_1800382B0
0x18003824c  cmp     byte ptr [r10+19h], 2
0x180038251  jb      short loc_1800382B0
0x180038253  mov     edx, 0Fh
0x180038258  jmp     short loc_18003829D
0x18003825a  mov     r8d, [rbx]; cbOutput
0x18003825d  xor     r9d, r9d; dwFlags
0x180038260  mov     rcx, [rsp+58h+phHash]; hHash
0x180038265  mov     rdx, rsi; pbOutput
0x180038268  call    cs:__imp_BCryptFinishHash
0x18003826e  mov     edi, eax
0x180038270  test    eax, eax
0x180038272  jns     short loc_1800382DB
0x180038274  mov     r10, cs:WPP_GLOBAL_Control
0x18003827b  lea     rcx, WPP_GLOBAL_Control
0x180038282  cmp     r10, rcx
0x180038285  jz      short loc_1800382B0
0x180038287  test    dword ptr [r10+1Ch], 40000h
0x18003828f  jz      short loc_1800382B0
0x180038291  cmp     byte ptr [r10+19h], 2
0x180038296  jb      short loc_1800382B0
0x180038298  mov     edx, 10h
0x18003829d  mov     rcx, [r10+10h]
0x1800382a1  lea     r8, WPP_2b8d55565e60367fc767d22ca087624d_Traceguids
0x1800382a8  mov     r9d, edi
0x1800382ab  call    WPP_SF_d
0x1800382b0  mov     ecx, edi; Status
0x1800382b2  call    cs:__imp_RtlNtStatusToDosError
0x1800382b8  mov     ebx, eax
0x1800382ba  mov     rcx, [rsp+58h+phHash]; hHash
0x1800382bf  test    rcx, rcx
0x1800382c2  jz      short loc_1800382CA
0x1800382c4  call    cs:__imp_BCryptDestroyHash
0x1800382ca  lea     rcx, CriticalSection; lpCriticalSection
0x1800382d1  call    cs:__imp_LeaveCriticalSection
0x1800382d7  mov     eax, ebx
0x1800382d9  jmp     short loc_180038304
0x1800382db  mov     rcx, [rsp+58h+phHash]; hHash
0x1800382e0  call    cs:__imp_BCryptDestroyHash
0x1800382e6  mov     eax, cs:dword_1800BC64C
0x1800382ec  lea     rcx, CriticalSection; lpCriticalSection
0x1800382f3  mov     [rbx], eax
0x1800382f5  call    cs:__imp_LeaveCriticalSection
0x1800382fb  xor     eax, eax
0x1800382fd  jmp     short loc_180038304
0x1800382ff  mov     eax, 57h ; 'W'
0x180038304  mov     rbx, [rsp+58h+arg_8]
0x180038309  mov     rbp, [rsp+58h+arg_10]
0x18003830e  add     rsp, 40h
0x180038312  pop     r14
0x180038314  pop     rdi
0x180038315  pop     rsi
0x180038316  retn
```
