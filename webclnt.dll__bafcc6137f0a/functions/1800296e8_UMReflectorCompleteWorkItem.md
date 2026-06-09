# UMReflectorCompleteWorkItem

- ea: `0x1800296e8`
- end: `0x1800297db`
- name: `UMReflectorCompleteWorkItem`
- size: `243`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000ca80`
- `0x18000ce10`

## callees

- `0x1800296e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800297b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800297b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029715`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180029715`
- `KERNEL32!LocalFree` at `0x1800297ab`
- `KERNEL32!LocalFree` at `0x1800297ab`

## pseudocode

```c
__int64 __fastcall UMReflectorCompleteWorkItem(__int64 a1, __int64 a2)
{
  __int64 v2; // rdi
  _QWORD *v3; // rbx
  _QWORD *v4; // rax
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  _QWORD *v7; // rdx
  __int64 v8; // rcx
  int v9; // ecx
  _QWORD *v10; // rbx
  _QWORD *v11; // rax

  if ( a1 && a2 )
  {
    v2 = *(_QWORD *)(a1 + 16);
    v3 = (_QWORD *)(a2 - 40);
    EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
    v4 = v3 + 2;
    v5 = v3[2];
    if ( *(_QWORD **)(v5 + 8) == v3 + 2 )
    {
      v6 = (_QWORD *)v3[3];
      if ( (_QWORD *)*v6 == v4 )
      {
        *v6 = v5;
        *(_QWORD *)(v5 + 8) = v6;
        if ( *(_DWORD *)(v2 + 64) || !*(_DWORD *)(v2 + 124) )
          goto LABEL_12;
        v7 = (_QWORD *)(v2 + 104);
        *((_DWORD *)v3 + 8) = 1;
        v8 = *(_QWORD *)(v2 + 104);
        if ( *(_QWORD *)(v8 + 8) == v2 + 104 )
        {
          *v4 = v8;
          v3[3] = v7;
          *(_QWORD *)(v8 + 8) = v4;
          *v7 = v4;
          v9 = *(_DWORD *)(v2 + 120);
          *(_DWORD *)(v2 + 120) = v9 + 1;
          if ( (unsigned int)(v9 + 1) < *(_DWORD *)(v2 + 124) )
          {
LABEL_14:
            LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 16));
            return 0;
          }
          *(_DWORD *)(v2 + 120) = v9;
          v10 = *(_QWORD **)(v2 + 112);
          if ( (_QWORD *)*v10 == v7 )
          {
            v11 = (_QWORD *)v10[1];
            if ( (_QWORD *)*v11 == v10 )
            {
              *(_QWORD *)(v2 + 112) = v11;
              v3 = v10 - 2;
              *v11 = v7;
LABEL_12:
              if ( v3 )
              {
                *((_DWORD *)v3 + 8) = 0;
                LocalFree(v3);
              }
              goto LABEL_14;
            }
          }
        }
      }
    }
    __fastfail(3u);
  }
  return 87;
}

```

## disassembly

```asm
0x1800296e8  mov     [rsp+arg_0], rbx
0x1800296ed  mov     [rsp+arg_8], rsi
0x1800296f2  push    rdi
0x1800296f3  sub     rsp, 20h
0x1800296f7  test    rcx, rcx
0x1800296fa  jz      loc_1800297C6
0x180029700  test    rdx, rdx
0x180029703  jz      loc_1800297C6
0x180029709  mov     rdi, [rcx+10h]
0x18002970d  lea     rbx, [rdx-28h]
0x180029711  lea     rcx, [rdi+10h]; lpCriticalSection
0x180029715  call    cs:__imp_EnterCriticalSection
0x18002971b  lea     rax, [rbx+10h]
0x18002971f  mov     rdx, [rax]
0x180029722  cmp     [rdx+8], rax
0x180029726  jnz     loc_1800297BF
0x18002972c  mov     rcx, [rax+8]
0x180029730  cmp     [rcx], rax
0x180029733  jnz     loc_1800297BF
0x180029739  mov     [rcx], rdx
0x18002973c  mov     [rdx+8], rcx
0x180029740  cmp     dword ptr [rdi+40h], 0
0x180029744  jnz     short loc_18002979C
0x180029746  cmp     dword ptr [rdi+7Ch], 0
0x18002974a  jbe     short loc_18002979C
0x18002974c  lea     rdx, [rdi+68h]
0x180029750  mov     dword ptr [rbx+20h], 1
0x180029757  mov     rcx, [rdx]
0x18002975a  cmp     [rcx+8], rdx
0x18002975e  jnz     short loc_1800297BF
0x180029760  mov     [rax], rcx
0x180029763  mov     [rax+8], rdx
0x180029767  mov     [rcx+8], rax
0x18002976b  mov     [rdx], rax
0x18002976e  mov     ecx, [rdi+78h]
0x180029771  lea     eax, [rcx+1]
0x180029774  mov     [rdi+78h], eax
0x180029777  cmp     eax, [rdi+7Ch]
0x18002977a  jb      short loc_1800297B1
0x18002977c  mov     [rdi+78h], ecx
0x18002977f  mov     rbx, [rdx+8]
0x180029783  cmp     [rbx], rdx
0x180029786  jnz     short loc_1800297BF
0x180029788  mov     rax, [rbx+8]
0x18002978c  cmp     [rax], rbx
0x18002978f  jnz     short loc_1800297BF
0x180029791  mov     [rdx+8], rax
0x180029795  add     rbx, 0FFFFFFFFFFFFFFF0h
0x180029799  mov     [rax], rdx
0x18002979c  test    rbx, rbx
0x18002979f  jz      short loc_1800297B1
0x1800297a1  mov     rcx, rbx; hMem
0x1800297a4  mov     dword ptr [rbx+20h], 0
0x1800297ab  call    cs:__imp_LocalFree
0x1800297b1  lea     rcx, [rdi+10h]; lpCriticalSection
0x1800297b5  call    cs:__imp_LeaveCriticalSection
0x1800297bb  xor     eax, eax
0x1800297bd  jmp     short loc_1800297CB
0x1800297bf  mov     ecx, 3
0x1800297c4  int     29h; Win8: RtlFailFast(ecx)
0x1800297c6  mov     eax, 57h ; 'W'
0x1800297cb  mov     rbx, [rsp+28h+arg_0]
0x1800297d0  mov     rsi, [rsp+28h+arg_8]
0x1800297d5  add     rsp, 20h
0x1800297d9  pop     rdi
0x1800297da  retn
```
