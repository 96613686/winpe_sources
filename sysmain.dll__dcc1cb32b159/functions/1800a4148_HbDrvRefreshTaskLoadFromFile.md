# HbDrvRefreshTaskLoadFromFile

- ea: `0x1800a4148`
- end: `0x1800a4417`
- name: `HbDrvRefreshTaskLoadFromFile`
- size: `719`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task`

## callers

- `0x1800a2f60`
- `0x1800a4420`
- `0x1800a5b88`

## callees

- `0x180074148`
- `0x180078746`
- `0x1800867c8`
- `0x18009f008`
- `0x1800a146c`
- `0x1800a4148`
- `0x1800b7010`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x1800a4198`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800a4198`
- `ntdll!RtlFreeUnicodeString` at `0x1800a43f7`
- `ntdll!RtlFreeUnicodeString` at `0x1800a43f7`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800a41cc`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800a41cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a41d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a41d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a4206`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a4206`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4222`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a4222`

## pseudocode

```c
__int64 __fastcall HbDrvRefreshTaskLoadFromFile(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        int a4,
        void **a5,
        unsigned int *a6,
        __int64 a7,
        int a8)
{
  char *v10; // rsi
  unsigned int v11; // r13d
  __int64 v13; // rcx
  unsigned int (__fastcall *v14)(__int64); // rax
  DWORD LastError; // ebx
  __int64 v16; // rbx
  size_t v17; // rbx
  _DWORD *v18; // rbx
  int v19; // r12d
  __int64 i; // rdi
  __int64 v21; // rax
  __int64 v22; // r14
  unsigned int v23; // r12d
  unsigned __int64 v24; // rdx
  __int64 v25; // r10
  unsigned int j; // ecx
  __int64 v27; // rax
  unsigned int k; // edi
  char v29; // cl
  __int64 v31; // [rsp+40h] [rbp-30h] BYREF
  __int128 v32; // [rsp+48h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-18h] BYREF
  int v34; // [rsp+B0h] [rbp+40h] BYREF
  int v35; // [rsp+C8h] [rbp+58h]

  v35 = a4;
  v34 = 0;
  v31 = 0;
  v10 = (char *)*a5;
  v11 = *a6;
  DestinationString = 0;
  RtlInitUnicodeStringEx(&DestinationString, 0);
  v13 = *(_QWORD *)(a1 + 16);
  v14 = *(unsigned int (__fastcall **)(__int64))a1;
  v32 = 0;
  if ( v14(v13) )
  {
    if ( RtlDosPathNameToNtPathName_U(a2, &DestinationString, 0, 0) )
    {
      v16 = DestinationString.Length >> 1;
      if ( v11 < (int)v16 + 1 )
      {
        if ( v10 )
        {
          HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v10);
          v11 = 0;
        }
        v10 = (char *)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 2LL * (unsigned int)(v16 + 1));
        if ( !v10 )
        {
          LastError = 8;
          goto LABEL_30;
        }
        v11 = v16 + 1;
      }
      v17 = 2 * v16;
      memcpy_0(v10, DestinationString.Buffer, v17);
      *(_WORD *)&v10[v17] = 0;
      v18 = (_DWORD *)(a3 + 36);
      v19 = *(_DWORD *)(a3 + 36);
      if ( !(unsigned int)PfsQueryFileExtentsTransparent(
                            (_DWORD)v10,
                            6,
                            (int)a3 + 8,
                            (int)a3 + 32,
                            a3 + 36,
                            (__int64)&v34,
                            (__int64)&v31) )
      {
        for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 28); i = (unsigned int)(i + 1) )
        {
          if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 48 * i + 8) + 8LL) == *v18 )
            break;
        }
        if ( *v18 != v19 )
        {
          PfsFileExtentDataCleanup(a3 + 16);
          *(_OWORD *)(a3 + 16) = 0;
        }
        if ( (_DWORD)i != *(_DWORD *)(a1 + 28) )
        {
          *(_DWORD *)a3 = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 48 * i + 28);
          *(_DWORD *)(a3 + 4) = *(_DWORD *)(*(_QWORD *)(a1 + 32) + 48 * i + 32);
          v21 = v31;
          *(_DWORD *)(a3 + 40) ^= (*(_DWORD *)(*(_QWORD *)(a1 + 32) + 48 * i + 40) ^ *(_DWORD *)(a3 + 40)) & 1;
          if ( !(unsigned int)HbDrvGetFileExtentData((_DWORD)v10, 6, a3, (unsigned int)&v32, v34, v21) )
          {
            v22 = a7;
            if ( !a7 )
              v22 = *(_QWORD *)(a1 + 48) + 104LL * (unsigned int)(6 * i - v35 + 5);
            v23 = DWORD2(v32);
            v24 = 0;
            v25 = v32;
            for ( j = 0; j < DWORD2(v32); v24 += *(_QWORD *)(16 * v27 + v32 + 8) )
              v27 = j++;
            if ( a8 || v24 <= 0x2000000 )
            {
              for ( k = 0; k < v23; ++k )
              {
                v29 = *(_BYTE *)(a1 + 24);
                LastError = HbDrvBitmapSetBitsCapped(
                              a1,
                              v22 + 24,
                              *(_QWORD *)(16LL * k + v25) >> v29,
                              ((unsigned int)(1 << v29)
                             + *(_QWORD *)(16LL * k + v25 + 8)
                             + (*(_QWORD *)(16LL * k + v25) & ((unsigned __int64)(unsigned int)(1 << v29) - 1))
                             - 1)
                            / (unsigned int)(1 << v29));
                if ( LastError )
                  goto LABEL_30;
                v25 = v32;
              }
            }
          }
        }
      }
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
    }
  }
  else
  {
    LastError = 995;
  }
LABEL_30:
  *a5 = v10;
  *a6 = v11;
  PfsFileExtentDataCleanup(&v32);
  RtlFreeUnicodeString(&DestinationString);
  return LastError;
}

```

## disassembly

```asm
0x1800a4148  mov     [rsp-38h+arg_8], rbx
0x1800a414d  mov     [rsp-38h+arg_18], r9d
0x1800a4152  push    rbp
0x1800a4153  push    rsi
0x1800a4154  push    rdi
0x1800a4155  push    r12
0x1800a4157  push    r13
0x1800a4159  push    r14
0x1800a415b  push    r15
0x1800a415d  mov     rbp, rsp
0x1800a4160  sub     rsp, 70h
0x1800a4164  mov     rsi, [rbp+arg_20]
0x1800a4168  mov     rbx, rdx
0x1800a416b  mov     r13, [rbp+arg_28]
0x1800a416f  mov     r15, rcx
0x1800a4172  xorps   xmm0, xmm0
0x1800a4175  mov     [rbp+arg_0], 0
0x1800a417c  xor     edx, edx; SourceString
0x1800a417e  mov     [rbp+var_30], 0
0x1800a4186  mov     rsi, [rsi]
0x1800a4189  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800a418d  mov     r13d, [r13+0]
0x1800a4191  mov     r14, r8
0x1800a4194  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800a4198  call    cs:__imp_RtlInitUnicodeStringEx
0x1800a419e  mov     rcx, [r15+10h]
0x1800a41a2  xorps   xmm0, xmm0
0x1800a41a5  mov     rax, [r15]
0x1800a41a8  movups  [rbp+var_28], xmm0
0x1800a41ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a41b1  test    eax, eax
0x1800a41b3  jnz     short loc_1800A41BF
0x1800a41b5  mov     ebx, 3E3h
0x1800a41ba  jmp     loc_1800A43DC
0x1800a41bf  xor     r9d, r9d; DirectoryInfo
0x1800a41c2  lea     rdx, [rbp+DestinationString]; NtPathName
0x1800a41c6  xor     r8d, r8d; NtFileNamePart
0x1800a41c9  mov     rcx, rbx; DosPathName
0x1800a41cc  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800a41d2  test    al, al
0x1800a41d4  jnz     short loc_1800A41E3
0x1800a41d6  call    cs:__imp_GetLastError
0x1800a41dc  mov     ebx, eax
0x1800a41de  jmp     loc_1800A43DC
0x1800a41e3  movzx   ebx, [rbp+DestinationString.Length]
0x1800a41e7  shr     ebx, 1
0x1800a41e9  lea     edi, [rbx+1]
0x1800a41ec  cmp     r13d, edi
0x1800a41ef  jnb     short loc_1800A423B
0x1800a41f1  test    rsi, rsi
0x1800a41f4  jz      short loc_1800A420F
0x1800a41f6  mov     rcx, cs:PfSvcGlobals
0x1800a41fd  mov     r8, rsi; lpMem
0x1800a4200  xor     edx, edx; dwFlags
0x1800a4202  mov     rcx, [rcx+58h]; hHeap
0x1800a4206  call    cs:__imp_HeapFree
0x1800a420c  xor     r13d, r13d
0x1800a420f  mov     rcx, cs:PfSvcGlobals
0x1800a4216  xor     edx, edx; dwFlags
0x1800a4218  mov     r8d, edi
0x1800a421b  add     r8, r8; dwBytes
0x1800a421e  mov     rcx, [rcx+58h]; hHeap
0x1800a4222  call    cs:__imp_HeapAlloc
0x1800a4228  mov     rsi, rax
0x1800a422b  test    rax, rax
0x1800a422e  jnz     short loc_1800A4238
0x1800a4230  lea     ebx, [rax+8]
0x1800a4233  jmp     loc_1800A43DC
0x1800a4238  mov     r13d, edi
0x1800a423b  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x1800a423f  add     rbx, rbx
0x1800a4242  mov     r8, rbx; Size
0x1800a4245  mov     rcx, rsi; void *
0x1800a4248  call    memcpy_0
0x1800a424d  xor     eax, eax
0x1800a424f  lea     r9, [r14+20h]
0x1800a4253  mov     [rbx+rsi], ax
0x1800a4257  lea     r8, [r14+8]
0x1800a425b  lea     rax, [rbp+var_30]
0x1800a425f  mov     edx, 6
0x1800a4264  mov     [rsp+70h+var_40], rax
0x1800a4269  lea     rbx, [r14+24h]
0x1800a426d  mov     r12d, [rbx]
0x1800a4270  lea     rax, [rbp+arg_0]
0x1800a4274  mov     [rsp+70h+var_48], rax
0x1800a4279  mov     rcx, rsi
0x1800a427c  mov     [rsp+70h+var_50], rbx
0x1800a4281  call    PfsQueryFileExtentsTransparent
0x1800a4286  test    eax, eax
0x1800a4288  jnz     loc_1800A43DA
0x1800a428e  xor     edi, edi
0x1800a4290  cmp     [r15+1Ch], edi
0x1800a4294  jbe     short loc_1800A42B5
0x1800a4296  mov     ecx, [rbx]
0x1800a4298  mov     rdx, [r15+20h]
0x1800a429c  lea     rax, [rdi+rdi*2]
0x1800a42a0  add     rax, rax
0x1800a42a3  mov     rax, [rdx+rax*8+8]
0x1800a42a8  cmp     [rax+8], ecx
0x1800a42ab  jz      short loc_1800A42B5
0x1800a42ad  inc     edi
0x1800a42af  cmp     edi, [r15+1Ch]
0x1800a42b3  jb      short loc_1800A429C
0x1800a42b5  cmp     [rbx], r12d
0x1800a42b8  jz      short loc_1800A42CB
0x1800a42ba  lea     rcx, [r14+10h]
0x1800a42be  call    PfsFileExtentDataCleanup
0x1800a42c3  xorps   xmm0, xmm0
0x1800a42c6  movups  xmmword ptr [r14+10h], xmm0
0x1800a42cb  cmp     edi, [r15+1Ch]
0x1800a42cf  jz      loc_1800A43DA
0x1800a42d5  mov     rax, [r15+20h]
0x1800a42d9  lea     r8, [rdi+rdi*2]
0x1800a42dd  shl     r8, 4
0x1800a42e1  lea     r9, [rbp+var_28]
0x1800a42e5  mov     edx, 6
0x1800a42ea  mov     ecx, [rax+r8+1Ch]
0x1800a42ef  mov     [r14], ecx
0x1800a42f2  mov     rax, [r15+20h]
0x1800a42f6  mov     ecx, [rax+r8+20h]
0x1800a42fb  mov     [r14+4], ecx
0x1800a42ff  mov     rax, [r15+20h]
0x1800a4303  mov     ecx, [r14+28h]
0x1800a4307  xor     ecx, [rax+r8+28h]
0x1800a430c  mov     r8, r14
0x1800a430f  mov     rax, [rbp+var_30]
0x1800a4313  and     ecx, 1
0x1800a4316  xor     [r14+28h], ecx
0x1800a431a  mov     rcx, rsi
0x1800a431d  mov     [rsp+70h+var_48], rax
0x1800a4322  mov     eax, [rbp+arg_0]
0x1800a4325  mov     dword ptr [rsp+70h+var_50], eax
0x1800a4329  call    HbDrvGetFileExtentData
0x1800a432e  test    eax, eax
0x1800a4330  jnz     loc_1800A43DA
0x1800a4336  mov     r14, [rbp+arg_30]
0x1800a433a  test    r14, r14
0x1800a433d  jnz     short loc_1800A4352
0x1800a433f  lea     eax, [rdi+rdi*2]
0x1800a4342  add     eax, eax
0x1800a4344  sub     eax, [rbp+arg_18]
0x1800a4347  add     eax, 5
0x1800a434a  imul    r14, rax, 68h ; 'h'
0x1800a434e  add     r14, [r15+30h]
0x1800a4352  mov     r12d, dword ptr [rbp+var_28+8]
0x1800a4356  xor     edx, edx
0x1800a4358  mov     r10, qword ptr [rbp+var_28]
0x1800a435c  xor     ecx, ecx
0x1800a435e  test    r12d, r12d
0x1800a4361  jz      short loc_1800A4375
0x1800a4363  mov     eax, ecx
0x1800a4365  inc     ecx
0x1800a4367  shl     rax, 4
0x1800a436b  add     rdx, [rax+r10+8]
0x1800a4370  cmp     ecx, r12d
0x1800a4373  jb      short loc_1800A4363
0x1800a4375  cmp     [rbp+arg_38], 0
0x1800a4379  jnz     short loc_1800A4384
0x1800a437b  cmp     rdx, 2000000h
0x1800a4382  ja      short loc_1800A43DA
0x1800a4384  xor     edi, edi
0x1800a4386  cmp     edi, r12d
0x1800a4389  jnb     short loc_1800A43DA
0x1800a438b  movzx   ecx, byte ptr [r15+18h]
0x1800a4390  mov     eax, 1
0x1800a4395  shl     eax, cl
0x1800a4397  mov     r9d, eax
0x1800a439a  dec     rax
0x1800a439d  mov     edx, edi
0x1800a439f  shl     rdx, 4
0x1800a43a3  mov     r8, [rdx+r10]
0x1800a43a7  and     rax, r8
0x1800a43aa  shr     r8, cl
0x1800a43ad  dec     rax
0x1800a43b0  mov     rcx, r15
0x1800a43b3  add     rax, [rdx+r10+8]
0x1800a43b8  xor     edx, edx
0x1800a43ba  add     rax, r9
0x1800a43bd  div     r9
0x1800a43c0  lea     rdx, [r14+18h]
0x1800a43c4  mov     r9, rax
0x1800a43c7  call    HbDrvBitmapSetBitsCapped
0x1800a43cc  mov     ebx, eax
0x1800a43ce  test    eax, eax
0x1800a43d0  jnz     short loc_1800A43DC
0x1800a43d2  mov     r10, qword ptr [rbp+var_28]
0x1800a43d6  inc     edi
0x1800a43d8  jmp     short loc_1800A4386
0x1800a43da  xor     ebx, ebx
0x1800a43dc  mov     rax, [rbp+arg_20]
0x1800a43e0  lea     rcx, [rbp+var_28]
0x1800a43e4  mov     [rax], rsi
0x1800a43e7  mov     rax, [rbp+arg_28]
0x1800a43eb  mov     [rax], r13d
0x1800a43ee  call    PfsFileExtentDataCleanup
0x1800a43f3  lea     rcx, [rbp+DestinationString]; UnicodeString
0x1800a43f7  call    cs:__imp_RtlFreeUnicodeString
0x1800a43fd  mov     eax, ebx
0x1800a43ff  mov     rbx, [rsp+70h+arg_8]
0x1800a4407  add     rsp, 70h
0x1800a440b  pop     r15
0x1800a440d  pop     r14
0x1800a440f  pop     r13
0x1800a4411  pop     r12
0x1800a4413  pop     rdi
0x1800a4414  pop     rsi
0x1800a4415  pop     rbp
0x1800a4416  retn
```
