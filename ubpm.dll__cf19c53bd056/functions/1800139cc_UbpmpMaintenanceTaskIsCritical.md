# UbpmpMaintenanceTaskIsCritical

- ea: `0x1800139cc`
- end: `0x180013b51`
- name: `UbpmpMaintenanceTaskIsCritical`
- size: `389`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014840`
- `0x18002cd60`
- `0x18002e764`

## callees

- `0x1800139cc`
- `0x1800143b0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013a91`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013b18`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013a91`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180013b18`

## pseudocode

```c
char __fastcall UbpmpMaintenanceTaskIsCritical(__int64 a1)
{
  unsigned __int16 i; // bx
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rcx
  const WCHAR *v6; // rdi
  const WCHAR *lpString2; // rbp
  __int64 v8; // rsi
  __int64 v9; // rbx
  __int64 cchCount2; // r9
  int v11; // eax
  PCNZWCH v13; // rdi
  const WCHAR *v14; // rbp
  __int64 v15; // rsi
  __int64 v16; // rbx
  __int64 v17; // r9
  int v18; // eax

  for ( i = 0; ; ++i )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( (unsigned int)i >= *(_DWORD *)(v3 + 32) )
      break;
    v4 = *(_QWORD *)(v3 + 40);
    if ( *(_DWORD *)(v4 + 40LL * i + 16) == 1 )
    {
      v5 = *(_QWORD *)(v4 + 40LL * i + 24);
      if ( *(_DWORD *)v5 == 2 )
      {
        if ( (unsigned int)UbpmpIsCriticalAction(*(UUID **)(v5 + 8)) )
          return 1;
      }
    }
  }
  v6 = g_CriticalMaintenanceTasks;
  if ( g_CriticalMaintenanceTasks )
  {
    lpString2 = *(const WCHAR **)(v3 + 8);
    if ( lpString2 )
    {
      v8 = -1;
      do
        ++v8;
      while ( lpString2[v8] );
      while ( *v6 )
      {
        v9 = -1;
        do
          ++v9;
        while ( v6[v9] );
        if ( (unsigned int)v8 >= (unsigned int)v9 )
        {
          cchCount2 = (unsigned int)(v9 - 1);
          if ( v6[cchCount2] == 42 )
          {
            v11 = CompareStringW(0x7Fu, 1u, v6, cchCount2, lpString2, cchCount2);
          }
          else
          {
            if ( (_DWORD)v8 != (_DWORD)v9 )
              goto LABEL_15;
            v11 = CompareStringW(0x7Fu, 1u, v6, v9, lpString2, v8);
          }
          if ( v11 == 2 )
            return 1;
        }
LABEL_15:
        v6 += (unsigned int)(v9 + 1);
      }
    }
  }
  v13 = g_CriticalTasks;
  if ( g_CriticalTasks )
  {
    v14 = *(const WCHAR **)(*(_QWORD *)(a1 + 24) + 8LL);
    if ( v14 )
    {
      v15 = -1;
      do
        ++v15;
      while ( v14[v15] );
      while ( 1 )
      {
        if ( !*v13 )
          return 0;
        v16 = -1;
        do
          ++v16;
        while ( v13[v16] );
        if ( (unsigned int)v15 >= (unsigned int)v16 )
        {
          v17 = (unsigned int)(v16 - 1);
          if ( v13[v17] == 42 )
          {
            v18 = CompareStringW(0x7Fu, 1u, v13, v17, v14, v17);
          }
          else
          {
            if ( (_DWORD)v15 != (_DWORD)v16 )
              goto LABEL_28;
            v18 = CompareStringW(0x7Fu, 1u, v13, v16, v14, v15);
          }
          if ( v18 == 2 )
            return 1;
        }
LABEL_28:
        v13 += (unsigned int)(v16 + 1);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800139cc  push    rbx
0x1800139ce  push    rbp
0x1800139cf  push    rsi
0x1800139d0  push    rdi
0x1800139d1  push    r12
0x1800139d3  push    r13
0x1800139d5  push    r14
0x1800139d7  push    r15
0x1800139d9  sub     rsp, 38h
0x1800139dd  xor     r15d, r15d
0x1800139e0  mov     r14, rcx
0x1800139e3  mov     ebx, r15d
0x1800139e6  lea     r12d, [r15+1]
0x1800139ea  mov     rdx, [r14+18h]
0x1800139ee  movzx   eax, bx
0x1800139f1  cmp     eax, [rdx+20h]
0x1800139f4  jnb     short loc_180013A25
0x1800139f6  movzx   eax, bx
0x1800139f9  lea     rcx, [rax+rax*4]
0x1800139fd  mov     rax, [rdx+28h]
0x180013a01  cmp     [rax+rcx*8+10h], r12d
0x180013a06  jnz     short loc_180013A1F
0x180013a08  mov     rcx, [rax+rcx*8+18h]
0x180013a0d  cmp     dword ptr [rcx], 2
0x180013a10  jnz     short loc_180013A1F
0x180013a12  mov     rcx, [rcx+8]; Uuid2
0x180013a16  call    ?UbpmpIsCriticalAction@@YAHPEAU_GUID@@@Z; UbpmpIsCriticalAction(_GUID *)
0x180013a1b  test    eax, eax
0x180013a1d  jnz     short loc_180013A9C
0x180013a1f  add     bx, r12w
0x180013a23  jmp     short loc_1800139EA
0x180013a25  mov     rdi, cs:?g_CriticalMaintenanceTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalMaintenanceTasks
0x180013a2c  or      r13, 0FFFFFFFFFFFFFFFFh
0x180013a30  test    rdi, rdi
0x180013a33  jz      short loc_180013AB0
0x180013a35  mov     rbp, [rdx+8]
0x180013a39  test    rbp, rbp
0x180013a3c  jz      short loc_180013AB0
0x180013a3e  mov     rsi, r13
0x180013a41  inc     rsi
0x180013a44  cmp     [rbp+rsi*2+0], r15w
0x180013a4a  jnz     short loc_180013A41
0x180013a4c  cmp     [rdi], r15w
0x180013a50  jz      short loc_180013AB0
0x180013a52  mov     rbx, r13
0x180013a55  inc     rbx
0x180013a58  cmp     [rdi+rbx*2], r15w
0x180013a5d  jnz     short loc_180013A55
0x180013a5f  cmp     esi, ebx
0x180013a61  jnb     short loc_180013A6C
0x180013a63  lea     eax, [rbx+1]
0x180013a66  lea     rdi, [rdi+rax*2]
0x180013a6a  jmp     short loc_180013A4C
0x180013a6c  lea     r9d, [rbx-1]; cchCount1
0x180013a70  cmp     word ptr [rdi+r9*2], 2Ah ; '*'
0x180013a76  jnz     loc_180013B30
0x180013a7c  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180013a81  mov     r8, rdi; lpString1
0x180013a84  mov     [rsp+78h+lpString2], rbp; lpString2
0x180013a89  mov     edx, r12d; dwCmpFlags
0x180013a8c  mov     ecx, 7Fh; Locale
0x180013a91  call    cs:__imp_CompareStringW
0x180013a97  cmp     eax, 2
0x180013a9a  jnz     short loc_180013A63
0x180013a9c  mov     al, r12b
0x180013a9f  add     rsp, 38h
0x180013aa3  pop     r15
0x180013aa5  pop     r14
0x180013aa7  pop     r13
0x180013aa9  pop     r12
0x180013aab  pop     rdi
0x180013aac  pop     rsi
0x180013aad  pop     rbp
0x180013aae  pop     rbx
0x180013aaf  retn
0x180013ab0  mov     rdi, cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalTasks
0x180013ab7  test    rdi, rdi
0x180013aba  jz      short loc_180013B29
0x180013abc  mov     rax, [r14+18h]
0x180013ac0  mov     rbp, [rax+8]
0x180013ac4  test    rbp, rbp
0x180013ac7  jz      short loc_180013B29
0x180013ac9  mov     rsi, r13
0x180013acc  inc     rsi
0x180013acf  cmp     [rbp+rsi*2+0], r15w
0x180013ad5  jnz     short loc_180013ACC
0x180013ad7  cmp     [rdi], r15w
0x180013adb  jz      short loc_180013B29
0x180013add  mov     rbx, r13
0x180013ae0  inc     rbx
0x180013ae3  cmp     [rdi+rbx*2], r15w
0x180013ae8  jnz     short loc_180013AE0
0x180013aea  cmp     esi, ebx
0x180013aec  jnb     short loc_180013AF7
0x180013aee  lea     eax, [rbx+1]
0x180013af1  lea     rdi, [rdi+rax*2]
0x180013af5  jmp     short loc_180013AD7
0x180013af7  lea     r9d, [rbx-1]; cchCount1
0x180013afb  cmp     word ptr [rdi+r9*2], 2Ah ; '*'
0x180013b01  jnz     short loc_180013B44
0x180013b03  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x180013b08  mov     r8, rdi; lpString1
0x180013b0b  mov     [rsp+78h+lpString2], rbp; lpString2
0x180013b10  mov     edx, r12d; dwCmpFlags
0x180013b13  mov     ecx, 7Fh; Locale
0x180013b18  call    cs:__imp_CompareStringW
0x180013b1e  cmp     eax, 2
0x180013b21  jz      loc_180013A9C
0x180013b27  jmp     short loc_180013AEE
0x180013b29  xor     al, al
0x180013b2b  jmp     loc_180013A9F
0x180013b30  cmp     esi, ebx
0x180013b32  jnz     loc_180013A63
0x180013b38  mov     [rsp+78h+cchCount2], esi
0x180013b3c  mov     r9d, ebx
0x180013b3f  jmp     loc_180013A81
0x180013b44  cmp     esi, ebx
0x180013b46  jnz     short loc_180013AEE
0x180013b48  mov     [rsp+78h+cchCount2], esi
0x180013b4c  mov     r9d, ebx
0x180013b4f  jmp     short loc_180013B08
```
