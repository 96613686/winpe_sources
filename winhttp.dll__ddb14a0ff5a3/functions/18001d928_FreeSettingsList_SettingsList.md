# FreeSettingsList(_SettingsList * *)

- ea: `0x18001d928`
- end: `0x18001dad8`
- name: `?FreeSettingsList@@YAXPEAPEAU_SettingsList@@@Z`
- size: `432`
- prototype: `void __fastcall(struct _SettingsList **)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001c588`
- `0x18001d690`
- `0x18006a0f0`

## callees

- `0x18001d928`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001daa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dabb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dacd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da85`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001daa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dabb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001dacd`

## pseudocode

```c
void __fastcall FreeSettingsList(LPVOID **a1)
{
  LPVOID *v1; // rsi
  unsigned int v2; // edx
  LPVOID *v3; // rdi
  unsigned int v4; // ebp
  __int64 v5; // rbx
  void **v6; // rax
  void *v7; // rcx
  void **v8; // rax
  void *v9; // rcx
  void **v10; // rax
  void *v11; // rcx
  void **v12; // rax
  void *v13; // rcx
  void **v14; // rax
  void *v15; // rcx
  void **v16; // rax
  void *v17; // rcx
  void **v18; // rax
  void *v19; // rcx
  void **v20; // rbx
  void *v21; // rcx

  if ( a1 )
  {
    v1 = *a1;
    *a1 = 0;
    if ( v1 )
    {
      v2 = *(_DWORD *)v1;
      v3 = v1 + 1;
      if ( *(_DWORD *)v1 )
      {
        v4 = 0;
        do
        {
          v5 = (__int64)*v3 + 112 * v4;
          if ( v5 )
          {
            v6 = (void **)(v5 + 16);
            if ( v5 != -16 )
            {
              v7 = *v6;
              if ( *v6 )
              {
                *v6 = 0;
                CoTaskMemFree(v7);
              }
            }
            v8 = (void **)(v5 + 24);
            if ( v5 != -24 )
            {
              v9 = *v8;
              if ( *v8 )
              {
                *v8 = 0;
                CoTaskMemFree(v9);
              }
            }
            v10 = (void **)(v5 + 32);
            if ( v5 != -32 )
            {
              v11 = *v10;
              if ( *v10 )
              {
                *v10 = 0;
                CoTaskMemFree(v11);
              }
            }
            v12 = (void **)(v5 + 64);
            if ( v5 != -64 )
            {
              v13 = *v12;
              if ( *v12 )
              {
                *v12 = 0;
                CoTaskMemFree(v13);
              }
            }
            v14 = (void **)(v5 + 40);
            if ( v5 != -40 )
            {
              v15 = *v14;
              if ( *v14 )
              {
                *v14 = 0;
                CoTaskMemFree(v15);
              }
            }
            v16 = (void **)(v5 + 48);
            if ( v5 != -48 )
            {
              v17 = *v16;
              if ( *v16 )
              {
                *v16 = 0;
                CoTaskMemFree(v17);
              }
            }
            v18 = (void **)(v5 + 88);
            if ( v5 != -88 )
            {
              v19 = *v18;
              if ( *v18 )
              {
                *v18 = 0;
                CoTaskMemFree(v19);
              }
            }
            v20 = (void **)(v5 + 104);
            if ( v20 )
            {
              v21 = *v20;
              if ( *v20 )
              {
                *v20 = 0;
                CoTaskMemFree(v21);
              }
            }
            v2 = *(_DWORD *)v1;
          }
          ++v4;
        }
        while ( v4 < v2 );
      }
      if ( v1 != (LPVOID *)-8LL )
      {
        if ( *v3 )
        {
          CoTaskMemFree(*v3);
          *v3 = 0;
        }
      }
      CoTaskMemFree(v1);
    }
  }
}

```

## disassembly

```asm
0x18001d928  test    rcx, rcx
0x18001d92b  jz      locret_18001DA47
0x18001d931  push    rbx
0x18001d932  push    rbp
0x18001d933  push    rsi
0x18001d934  push    rdi
0x18001d935  sub     rsp, 28h
0x18001d939  mov     rsi, [rcx]
0x18001d93c  mov     qword ptr [rcx], 0
0x18001d943  test    rsi, rsi
0x18001d946  jz      loc_18001DA3F
0x18001d94c  mov     edx, [rsi]
0x18001d94e  lea     rdi, [rsi+8]
0x18001d952  test    edx, edx
0x18001d954  jz      loc_18001DA1C
0x18001d95a  xor     ebp, ebp
0x18001d95c  mov     eax, ebp
0x18001d95e  imul    rbx, rax, 70h ; 'p'
0x18001d962  add     rbx, [rdi]
0x18001d965  jz      loc_18001DA12
0x18001d96b  lea     rax, [rbx+10h]
0x18001d96f  test    rax, rax
0x18001d972  jz      short loc_18001D980
0x18001d974  mov     rcx, [rax]; pv
0x18001d977  test    rcx, rcx
0x18001d97a  jnz     loc_18001DA48
0x18001d980  lea     rax, [rbx+18h]
0x18001d984  test    rax, rax
0x18001d987  jz      short loc_18001D995
0x18001d989  mov     rcx, [rax]; pv
0x18001d98c  test    rcx, rcx
0x18001d98f  jnz     loc_18001DA5A
0x18001d995  lea     rax, [rbx+20h]
0x18001d999  test    rax, rax
0x18001d99c  jz      short loc_18001D9AA
0x18001d99e  mov     rcx, [rax]; pv
0x18001d9a1  test    rcx, rcx
0x18001d9a4  jnz     loc_18001DA6C
0x18001d9aa  lea     rax, [rbx+40h]
0x18001d9ae  test    rax, rax
0x18001d9b1  jz      short loc_18001D9BF
0x18001d9b3  mov     rcx, [rax]; pv
0x18001d9b6  test    rcx, rcx
0x18001d9b9  jnz     loc_18001DA7E
0x18001d9bf  lea     rax, [rbx+28h]
0x18001d9c3  test    rax, rax
0x18001d9c6  jz      short loc_18001D9D4
0x18001d9c8  mov     rcx, [rax]; pv
0x18001d9cb  test    rcx, rcx
0x18001d9ce  jnz     loc_18001DA90
0x18001d9d4  lea     rax, [rbx+30h]
0x18001d9d8  test    rax, rax
0x18001d9db  jz      short loc_18001D9E9
0x18001d9dd  mov     rcx, [rax]; pv
0x18001d9e0  test    rcx, rcx
0x18001d9e3  jnz     loc_18001DAA2
0x18001d9e9  lea     rax, [rbx+58h]
0x18001d9ed  test    rax, rax
0x18001d9f0  jz      short loc_18001D9FE
0x18001d9f2  mov     rcx, [rax]; pv
0x18001d9f5  test    rcx, rcx
0x18001d9f8  jnz     loc_18001DAB4
0x18001d9fe  add     rbx, 68h ; 'h'
0x18001da02  jz      short loc_18001DA10
0x18001da04  mov     rcx, [rbx]; pv
0x18001da07  test    rcx, rcx
0x18001da0a  jnz     loc_18001DAC6
0x18001da10  mov     edx, [rsi]
0x18001da12  inc     ebp
0x18001da14  cmp     ebp, edx
0x18001da16  jb      loc_18001D95C
0x18001da1c  test    rdi, rdi
0x18001da1f  jz      short loc_18001DA36
0x18001da21  mov     rcx, [rdi]; pv
0x18001da24  test    rcx, rcx
0x18001da27  jz      short loc_18001DA36
0x18001da29  call    cs:__imp_CoTaskMemFree
0x18001da2f  mov     qword ptr [rdi], 0
0x18001da36  mov     rcx, rsi; pv
0x18001da39  call    cs:__imp_CoTaskMemFree
0x18001da3f  add     rsp, 28h
0x18001da43  pop     rdi
0x18001da44  pop     rsi
0x18001da45  pop     rbp
0x18001da46  pop     rbx
0x18001da47  retn
0x18001da48  mov     qword ptr [rax], 0
0x18001da4f  call    cs:__imp_CoTaskMemFree
0x18001da55  jmp     loc_18001D980
0x18001da5a  mov     qword ptr [rax], 0
0x18001da61  call    cs:__imp_CoTaskMemFree
0x18001da67  jmp     loc_18001D995
0x18001da6c  mov     qword ptr [rax], 0
0x18001da73  call    cs:__imp_CoTaskMemFree
0x18001da79  jmp     loc_18001D9AA
0x18001da7e  mov     qword ptr [rax], 0
0x18001da85  call    cs:__imp_CoTaskMemFree
0x18001da8b  jmp     loc_18001D9BF
0x18001da90  mov     qword ptr [rax], 0
0x18001da97  call    cs:__imp_CoTaskMemFree
0x18001da9d  jmp     loc_18001D9D4
0x18001daa2  mov     qword ptr [rax], 0
0x18001daa9  call    cs:__imp_CoTaskMemFree
0x18001daaf  jmp     loc_18001D9E9
0x18001dab4  mov     qword ptr [rax], 0
0x18001dabb  call    cs:__imp_CoTaskMemFree
0x18001dac1  jmp     loc_18001D9FE
0x18001dac6  mov     qword ptr [rbx], 0
0x18001dacd  call    cs:__imp_CoTaskMemFree
0x18001dad3  jmp     loc_18001DA10
```
