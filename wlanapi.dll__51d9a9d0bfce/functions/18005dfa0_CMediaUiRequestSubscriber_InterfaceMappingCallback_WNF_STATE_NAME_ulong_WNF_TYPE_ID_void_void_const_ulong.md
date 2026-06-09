# CMediaUiRequestSubscriber::InterfaceMappingCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x18005dfa0`
- end: `0x18005e0eb`
- name: `?InterfaceMappingCallback@CMediaUiRequestSubscriber@@AEAAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `331`
- prototype: `__int64 __usercall@<rax>(CMediaUiRequestSubscriber *__hidden this@<rcx>, struct _WNF_STATE_NAME@<rdx>, unsigned int@<r8d>, struct _WNF_TYPE_ID *@<r9>, void *, const void *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005dde8`
- `0x18005e100`

## callees

- `0x18005dc3c`
- `0x18005dfa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e008`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e008`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e0ce`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e0ce`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005e05f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005e098`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005e05f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18005e098`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMediaUiRequestSubscriber::InterfaceMappingCallback(
        CMediaUiRequestSubscriber *this,
        struct _WNF_STATE_NAME a2,
        __int64 a3,
        struct _WNF_TYPE_ID *a4,
        void *a5,
        char *a6,
        unsigned int a7)
{
  FILETIME *v8; // r15
  unsigned int v9; // edi
  char v10; // r14
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  unsigned int v12; // edi
  unsigned int v13; // ebp
  char *v14; // r12
  __int64 v15; // r14
  __int64 v16; // rax
  const FILETIME *v17; // r13
  int v18; // eax
  char v20; // [rsp+70h] [rbp+18h]
  FILETIME FileTime1; // [rsp+78h] [rbp+20h] BYREF

  FileTime1 = (FILETIME)a4;
  v8 = (FILETIME *)((char *)this + 88);
  FileTime1 = (FILETIME)*((_QWORD *)this + 11);
  if ( !*((_DWORD *)this + 5) )
  {
    v9 = a7;
    if ( a7 )
    {
      if ( (a7 & 0x1F) == 0 )
      {
        v10 = 0;
        v20 = 0;
        v11 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        v12 = v9 >> 5;
        v13 = 0;
        v14 = a6;
        while ( v13 < v12 )
        {
          if ( *((_DWORD *)this + 5) )
            goto LABEL_20;
          v15 = 32LL * v13;
          v16 = *(_QWORD *)&v14[v15] - NullGuid;
          if ( !v16 )
            v16 = *(_QWORD *)&v14[v15 + 8];
          if ( !v16 )
          {
            v10 = v20;
            break;
          }
          v17 = (const FILETIME *)&v14[v15];
          if ( CompareFileTime(v8, (const FILETIME *)&v14[v15 + 24]) >= 0 )
          {
            v10 = v20;
          }
          else
          {
            v18 = CMediaUiRequestSubscriber::AddInterfaceStateSubscription(
                    this,
                    *(struct _WNF_STATE_NAME *)&v14[v15 + 16]);
            v10 = v20;
            if ( v18 < 0 )
              v10 = 1;
            v20 = v10;
            if ( CompareFileTime(&FileTime1, v17 + 3) < 0 )
              FileTime1 = v17[3];
          }
          ++v13;
        }
        if ( !v10 )
          *v8 = FileTime1;
LABEL_20:
        LeaveCriticalSection(v11);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005dfa0  mov     r11, rsp
0x18005dfa3  mov     [r11+8], rbx
0x18005dfa7  mov     [r11+20h], r9
0x18005dfab  mov     [r11+18h], r8d
0x18005dfaf  mov     [r11+10h], rdx
0x18005dfb3  push    rbp
0x18005dfb4  push    rsi
0x18005dfb5  push    rdi
0x18005dfb6  push    r12
0x18005dfb8  push    r13
0x18005dfba  push    r14
0x18005dfbc  push    r15
0x18005dfbe  sub     rsp, 20h
0x18005dfc2  mov     rsi, rcx
0x18005dfc5  lea     r15, [rcx+58h]
0x18005dfc9  mov     rax, [r15]
0x18005dfcc  mov     [r11+20h], rax
0x18005dfd0  mov     eax, [rcx+14h]
0x18005dfd3  test    eax, eax
0x18005dfd5  jnz     loc_18005E0D4
0x18005dfdb  mov     edi, [rsp+58h+arg_30]
0x18005dfe2  test    edi, edi
0x18005dfe4  jz      loc_18005E0D4
0x18005dfea  test    dil, 1Fh
0x18005dfee  jnz     loc_18005E0D4
0x18005dff4  xor     r14b, r14b
0x18005dff7  mov     [rsp+58h+arg_10], r14d
0x18005dffc  lea     rbx, [rcx+20h]
0x18005e000  mov     [rsp+58h+arg_8], rbx
0x18005e005  mov     rcx, rbx; lpCriticalSection
0x18005e008  call    cs:__imp_EnterCriticalSection
0x18005e00e  nop
0x18005e00f  shr     edi, 5
0x18005e012  xor     ebp, ebp
0x18005e014  mov     r12, [rsp+58h+arg_28]
0x18005e01c  cmp     ebp, edi
0x18005e01e  jnb     loc_18005E0BE
0x18005e024  mov     eax, [rsi+14h]
0x18005e027  test    eax, eax
0x18005e029  jnz     loc_18005E0CB
0x18005e02f  mov     r14d, ebp
0x18005e032  shl     r14, 5
0x18005e036  mov     rax, [r14+r12]
0x18005e03a  sub     rax, cs:NullGuid
0x18005e041  jnz     short loc_18005E04F
0x18005e043  mov     rax, [r14+r12+8]
0x18005e048  sub     rax, cs:qword_180072A78
0x18005e04f  test    rax, rax
0x18005e052  jz      short loc_18005E0B9
0x18005e054  lea     r13, [r14+r12]
0x18005e058  lea     rdx, [r13+18h]; lpFileTime2
0x18005e05c  mov     rcx, r15; lpFileTime1
0x18005e05f  call    cs:__imp_CompareFileTime
0x18005e065  test    eax, eax
0x18005e067  jns     short loc_18005E0AD
0x18005e069  mov     rdx, [r14+r12+10h]; struct _WNF_STATE_NAME
0x18005e06e  mov     rcx, rsi; this
0x18005e071  call    ?AddInterfaceStateSubscription@CMediaUiRequestSubscriber@@AEAAJU_WNF_STATE_NAME@@@Z; CMediaUiRequestSubscriber::AddInterfaceStateSubscription(_WNF_STATE_NAME)
0x18005e076  mov     r14d, [rsp+58h+arg_10]
0x18005e07b  movzx   r14d, r14b
0x18005e07f  test    eax, eax
0x18005e081  mov     eax, 1
0x18005e086  cmovs   r14d, eax
0x18005e08a  mov     [rsp+58h+arg_10], r14d
0x18005e08f  lea     rdx, [r13+18h]; lpFileTime2
0x18005e093  lea     rcx, [rsp+58h+FileTime1]; lpFileTime1
0x18005e098  call    cs:__imp_CompareFileTime
0x18005e09e  test    eax, eax
0x18005e0a0  jns     short loc_18005E0B2
0x18005e0a2  mov     rax, [r13+18h]
0x18005e0a6  mov     qword ptr [rsp+58h+FileTime1.dwLowDateTime], rax
0x18005e0ab  jmp     short loc_18005E0B2
0x18005e0ad  mov     r14d, [rsp+58h+arg_10]
0x18005e0b2  inc     ebp
0x18005e0b4  jmp     loc_18005E01C
0x18005e0b9  mov     r14d, [rsp+58h+arg_10]
0x18005e0be  test    r14b, r14b
0x18005e0c1  jnz     short loc_18005E0CB
0x18005e0c3  mov     rax, qword ptr [rsp+58h+FileTime1.dwLowDateTime]
0x18005e0c8  mov     [r15], rax
0x18005e0cb  mov     rcx, rbx; lpCriticalSection
0x18005e0ce  call    cs:__imp_LeaveCriticalSection
0x18005e0d4  xor     eax, eax
0x18005e0d6  mov     rbx, [rsp+58h+arg_0]
0x18005e0db  add     rsp, 20h
0x18005e0df  pop     r15
0x18005e0e1  pop     r14
0x18005e0e3  pop     r13
0x18005e0e5  pop     r12
0x18005e0e7  pop     rdi
0x18005e0e8  pop     rsi
0x18005e0e9  pop     rbp
0x18005e0ea  retn
```
