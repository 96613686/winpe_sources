# SampAlQueryAliasMembership(void *,_SAMPR_PSID_ARRAY *,_SAMPR_ULONG_ARRAY *)

- ea: `0x18001f950`
- end: `0x18001fd2d`
- name: `?SampAlQueryAliasMembership@@YAJPEAXPEAU_SAMPR_PSID_ARRAY@@PEAU_SAMPR_ULONG_ARRAY@@@Z`
- size: `989`
- prototype: `__int64 __fastcall(unsigned int *, struct _SAMPR_PSID_ARRAY *, struct _SAMPR_ULONG_ARRAY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009030`

## callees

- `0x18001f950`
- `0x180027e24`
- `0x1800bb794`

## import_xrefs

- `ntdll!RtlSubAuthorityCountSid` at `0x18001fa30`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001fa85`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001fa30`
- `ntdll!RtlSubAuthorityCountSid` at `0x18001fa85`
- `ntdll!RtlSubAuthoritySid` at `0x18001fa93`
- `ntdll!RtlSubAuthoritySid` at `0x18001fa93`
- `ntdll!RtlLengthRequiredSid` at `0x18001f9b5`
- `ntdll!RtlLengthRequiredSid` at `0x18001f9b5`
- `ntdll!RtlLengthSid` at `0x18001fa49`
- `ntdll!RtlLengthSid` at `0x18001fb5a`
- `ntdll!RtlLengthSid` at `0x18001fa49`
- `ntdll!RtlLengthSid` at `0x18001fb5a`
- `ntdll!RtlEqualSid` at `0x18001faf2`
- `ntdll!RtlEqualSid` at `0x18001faf2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f9c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f9de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fa5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f9c2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001f9de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fa5f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fc47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fcb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fcc9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fc47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fcb2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fcc9`

## pseudocode

```c
__int64 __fastcall SampAlQueryAliasMembership(
        unsigned int *a1,
        struct _SAMPR_PSID_ARRAY *a2,
        struct _SAMPR_ULONG_ARRAY *a3)
{
  struct _SAMPR_PSID_ARRAY *v4; // r13
  __int64 v5; // r14
  ULONG v6; // eax
  HLOCAL v7; // rsi
  HLOCAL v8; // rax
  int v9; // edi
  unsigned int v10; // eax
  ULONG v11; // r12d
  char *v12; // r15
  void *v13; // rdi
  int v14; // ebp
  size_t v15; // r15
  PUCHAR v16; // rax
  PULONG v17; // rax
  int v18; // edi
  unsigned int *v19; // rbp
  int v20; // edi
  unsigned int v21; // edi
  char *v22; // rcx
  __int64 v23; // rbp
  unsigned int v24; // r13d
  int v25; // r12d
  __int64 v26; // r8
  unsigned int v27; // edx
  HLOCAL v28; // rax
  HLOCAL v29; // r15
  void *v30; // rcx
  char *v32; // [rsp+30h] [rbp-58h]
  int v33; // [rsp+90h] [rbp+8h]
  unsigned int v35; // [rsp+A0h] [rbp+18h]
  ULONG v36; // [rsp+A8h] [rbp+20h]

  v4 = a2;
  *(_DWORD *)a3 = 0;
  *((_QWORD *)a3 + 1) = 0;
  v5 = *((_QWORD *)SampDefinedDomains + 170 * a1[50] + 158);
  if ( *(_DWORD *)(v5 + 16) )
  {
    v6 = RtlLengthRequiredSid(0x100u);
    v7 = LocalAlloc(0x40u, v6);
    if ( v7 && (v8 = LocalAlloc(0x40u, 0x28u), (*((_QWORD *)a3 + 1) = v8) != 0) )
    {
      v9 = 0;
      if ( !*(_DWORD *)v4 )
      {
LABEL_52:
        LocalFree(v7);
        goto LABEL_54;
      }
      v10 = 0;
      v36 = 0;
      v35 = 0;
      v11 = 0;
      v12 = 0;
      v32 = 0;
      v33 = 10;
      do
      {
        v13 = *(void **)(*((_QWORD *)v4 + 1) + 8LL * v10);
        v14 = *RtlSubAuthorityCountSid(v13);
        if ( (_BYTE)v14 )
        {
          v15 = RtlLengthSid(v13);
          memmove_0(v7, v13, v15);
          v16 = RtlSubAuthorityCountSid(v7);
          --*v16;
          v17 = RtlSubAuthoritySid(v13, v14 - 1);
          v9 = 0;
          v11 = *v17;
          v36 = *v17;
          v12 = v32;
        }
        else
        {
          v9 = -1073741704;
        }
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            128,
            WPP_48bf36016493398285a8dbc678e80a21_Traceguids,
            (unsigned int)v9,
            v9);
        if ( v9 < 0 )
          break;
        v18 = 0;
        v19 = (unsigned int *)(v5 + 20);
        while ( v18 < *(_DWORD *)(v5 + 16) )
        {
          if ( RtlEqualSid(v7, v19 + 4) )
          {
            v20 = 0;
            goto LABEL_18;
          }
          ++v18;
          v19 = (unsigned int *)((char *)v19 + v19[1]);
        }
        v20 = -1073741601;
        v19 = 0;
LABEL_18:
        if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
          WPP_SF_Dd(
            WPP_GLOBAL_Control[3].Buffer,
            39,
            WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids,
            (unsigned int)v20,
            v20);
        if ( v20 >= 0 )
        {
          v21 = 0;
          v22 = (char *)v19 + RtlLengthSid(v19 + 4) + 16;
          while ( v21 < v19[3] )
          {
            if ( v11 == *((_DWORD *)v22 + 3) )
            {
              v12 = v22;
              v32 = v22;
              v9 = 0;
              goto LABEL_28;
            }
            ++v21;
            v22 += *((unsigned int *)v22 + 1);
          }
          v9 = -1073741446;
LABEL_28:
          if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
            WPP_SF_Dd(
              WPP_GLOBAL_Control[3].Buffer,
              31,
              WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids,
              (unsigned int)v9,
              v9);
          if ( v9 >= 0 )
          {
            v23 = 0;
            if ( *((_DWORD *)v12 + 4) )
            {
              v24 = v33;
              while ( 2 )
              {
                v25 = *(_DWORD *)&v12[4 * v23 + 20];
                v26 = 0;
                v27 = *(_DWORD *)a3;
                while ( (unsigned int)v26 < v27 )
                {
                  if ( v25 == *(_DWORD *)(*((_QWORD *)a3 + 1) + 4 * v26) )
                    goto LABEL_42;
                  v26 = (unsigned int)(v26 + 1);
                }
                if ( v27 == v24 )
                {
                  v24 += 10;
                  v28 = LocalAlloc(0x40u, 4LL * v24);
                  v29 = v28;
                  v9 = -1073741801;
                  if ( !v28 )
                  {
                    v12 = v32;
                    break;
                  }
                  v9 = 0;
                  memmove_0(v28, *((const void **)a3 + 1), 4LL * *(unsigned int *)a3);
                  LocalFree(*((HLOCAL *)a3 + 1));
                  *((_QWORD *)a3 + 1) = v29;
                  v12 = v32;
                }
                *(_DWORD *)(*((_QWORD *)a3 + 1) + 4LL * (unsigned int)(*(_DWORD *)a3)++) = v25;
LABEL_42:
                v23 = (unsigned int)(v23 + 1);
                if ( (unsigned int)v23 < *((_DWORD *)v12 + 4) )
                  continue;
                break;
              }
              v33 = v24;
              v4 = a2;
            }
          }
          else
          {
            v9 = 0;
          }
        }
        else
        {
          v9 = 0;
        }
        v11 = v36;
        v10 = v35 + 1;
        v35 = v10;
      }
      while ( v10 < *(_DWORD *)v4 );
    }
    else
    {
      v30 = (void *)*((_QWORD *)a3 + 1);
      if ( v30 )
      {
        LocalFree(v30);
        *((_QWORD *)a3 + 1) = 0;
      }
      v9 = -1073741801;
    }
    if ( !v7 )
      goto LABEL_54;
    goto LABEL_52;
  }
  v9 = 0;
LABEL_54:
  if ( (*(_DWORD *)(&WPP_GLOBAL_Control[4].MaximumLength + 1) & 0x20000) != 0 )
    WPP_SF_Dd(WPP_GLOBAL_Control[3].Buffer, 16, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids, (unsigned int)v9, v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001f950  mov     rax, rsp
0x18001f953  mov     [rax+10h], rdx
0x18001f957  push    rdi
0x18001f958  sub     rsp, 80h
0x18001f95f  mov     [rax-10h], rbx
0x18001f963  mov     rbx, r8
0x18001f966  mov     [rax-18h], rbp
0x18001f96a  xor     ebp, ebp
0x18001f96c  mov     [rax-20h], rsi
0x18001f970  mov     [rax-28h], r12
0x18001f974  mov     [rax-30h], r13
0x18001f978  mov     r13, rdx
0x18001f97b  mov     [rax-38h], r14
0x18001f97f  mov     [r8], ebp
0x18001f982  mov     [r8+8], rbp
0x18001f986  mov     [rax-40h], r15
0x18001f98a  mov     eax, [rcx+0C8h]
0x18001f990  imul    rcx, rax, 550h
0x18001f997  mov     rax, cs:?SampDefinedDomains@@3PEAU_PSAMP_DEFINED_DOMAINS@@EA; _PSAMP_DEFINED_DOMAINS * SampDefinedDomains
0x18001f99e  mov     r14, [rcx+rax+4F0h]
0x18001f9a6  cmp     [r14+10h], ebp
0x18001f9aa  jz      loc_18001FCD1
0x18001f9b0  mov     ecx, 100h; SubAuthorityCount
0x18001f9b5  call    cs:__imp_RtlLengthRequiredSid
0x18001f9bb  mov     edx, eax; uBytes
0x18001f9bd  mov     ecx, 40h ; '@'; uFlags
0x18001f9c2  call    cs:__imp_LocalAlloc
0x18001f9c8  mov     rsi, rax
0x18001f9cb  test    rax, rax
0x18001f9ce  jz      loc_18001FCA9
0x18001f9d4  mov     edx, 28h ; '('; uBytes
0x18001f9d9  mov     ecx, 40h ; '@'; uFlags
0x18001f9de  call    cs:__imp_LocalAlloc
0x18001f9e4  mov     [rbx+8], rax
0x18001f9e8  test    rax, rax
0x18001f9eb  jz      loc_18001FCA9
0x18001f9f1  mov     edi, ebp
0x18001f9f3  cmp     [r13+0], ebp
0x18001f9f7  jbe     loc_18001FCC6
0x18001f9fd  mov     eax, ebp
0x18001f9ff  mov     [rsp+88h+arg_18], ebp
0x18001fa06  mov     [rsp+88h+arg_10], eax
0x18001fa0d  mov     r12d, ebp
0x18001fa10  mov     r15d, ebp
0x18001fa13  mov     [rsp+88h+var_58], rbp
0x18001fa18  mov     [rsp+88h+arg_0], 0Ah
0x18001fa23  mov     ecx, eax
0x18001fa25  mov     rax, [r13+8]
0x18001fa29  mov     rdi, [rax+rcx*8]
0x18001fa2d  mov     rcx, rdi; Sid
0x18001fa30  call    cs:__imp_RtlSubAuthorityCountSid
0x18001fa36  movzx   ebp, byte ptr [rax]
0x18001fa39  cmp     bpl, 1
0x18001fa3d  jnb     short loc_18001FA46
0x18001fa3f  mov     edi, 0C0000078h
0x18001fa44  jmp     short loc_18001FAAB
0x18001fa46  mov     rcx, rdi; Sid
0x18001fa49  call    cs:__imp_RtlLengthSid
0x18001fa4f  mov     r15d, eax
0x18001fa52  test    rsi, rsi
0x18001fa55  jnz     short loc_18001FA74
0x18001fa57  mov     edx, r15d; uBytes
0x18001fa5a  mov     ecx, 40h ; '@'; uFlags
0x18001fa5f  call    cs:__imp_LocalAlloc
0x18001fa65  mov     rsi, rax
0x18001fa68  test    rax, rax
0x18001fa6b  jnz     short loc_18001FA74
0x18001fa6d  mov     edi, 0C000009Ah
0x18001fa72  jmp     short loc_18001FAA6
0x18001fa74  mov     r8, r15; Size
0x18001fa77  mov     rdx, rdi; Src
0x18001fa7a  mov     rcx, rsi; void *
0x18001fa7d  call    memmove_0
0x18001fa82  mov     rcx, rsi; Sid
0x18001fa85  call    cs:__imp_RtlSubAuthorityCountSid
0x18001fa8b  lea     edx, [rbp-1]; SubAuthority
0x18001fa8e  mov     rcx, rdi; Sid
0x18001fa91  dec     byte ptr [rax]
0x18001fa93  call    cs:__imp_RtlSubAuthoritySid
0x18001fa99  xor     edi, edi
0x18001fa9b  mov     r12d, [rax]
0x18001fa9e  mov     [rsp+88h+arg_18], r12d
0x18001faa6  mov     r15, [rsp+88h+var_58]
0x18001faab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fab2  test    dword ptr [rcx+44h], 20000h
0x18001fab9  jz      short loc_18001FAD7
0x18001fabb  mov     rcx, [rcx+38h]
0x18001fabf  lea     r8, WPP_48bf36016493398285a8dbc678e80a21_Traceguids
0x18001fac6  mov     edx, 80h
0x18001facb  mov     [rsp+88h+var_68], edi
0x18001facf  mov     r9d, edi
0x18001fad2  call    WPP_SF_Dd
0x18001fad7  test    edi, edi
0x18001fad9  js      loc_18001FCC1
0x18001fadf  xor     edi, edi
0x18001fae1  lea     rbp, [r14+14h]
0x18001fae5  cmp     edi, [r14+10h]
0x18001fae9  jge     short loc_18001FB0A
0x18001faeb  lea     rdx, [rbp+10h]; Sid2
0x18001faef  mov     rcx, rsi; Sid1
0x18001faf2  call    cs:__imp_RtlEqualSid
0x18001faf8  test    al, al
0x18001fafa  jnz     short loc_18001FB06
0x18001fafc  mov     eax, [rbp+4]
0x18001faff  inc     edi
0x18001fb01  add     rbp, rax
0x18001fb04  jmp     short loc_18001FAE5
0x18001fb06  xor     edi, edi
0x18001fb08  jmp     short loc_18001FB11
0x18001fb0a  mov     edi, 0C00000DFh
0x18001fb0f  xor     ebp, ebp
0x18001fb11  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb18  test    dword ptr [rcx+44h], 20000h
0x18001fb1f  jz      short loc_18001FB3D
0x18001fb21  mov     rcx, [rcx+38h]
0x18001fb25  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x18001fb2c  mov     edx, 27h ; '''
0x18001fb31  mov     [rsp+88h+var_68], edi
0x18001fb35  mov     r9d, edi
0x18001fb38  call    WPP_SF_Dd
0x18001fb3d  test    edi, edi
0x18001fb3f  jns     short loc_18001FB54
0x18001fb41  cmp     edi, 0C00000DFh
0x18001fb47  jnz     loc_18001FCC1
0x18001fb4d  xor     edi, edi
0x18001fb4f  jmp     loc_18001FC85
0x18001fb54  lea     rcx, [rbp+10h]; Sid
0x18001fb58  xor     edi, edi
0x18001fb5a  call    cs:__imp_RtlLengthSid
0x18001fb60  mov     edx, [rbp+0Ch]
0x18001fb63  mov     ecx, eax
0x18001fb65  add     rcx, 10h
0x18001fb69  add     rcx, rbp
0x18001fb6c  cmp     edi, edx
0x18001fb6e  jnb     short loc_18001FB8C
0x18001fb70  cmp     r12d, [rcx+0Ch]
0x18001fb74  jz      short loc_18001FB80
0x18001fb76  mov     eax, [rcx+4]
0x18001fb79  inc     edi
0x18001fb7b  add     rcx, rax
0x18001fb7e  jmp     short loc_18001FB6C
0x18001fb80  mov     r15, rcx
0x18001fb83  mov     [rsp+88h+var_58], rcx
0x18001fb88  xor     edi, edi
0x18001fb8a  jmp     short loc_18001FB91
0x18001fb8c  mov     edi, 0C000017Ah
0x18001fb91  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb98  test    dword ptr [rcx+44h], 20000h
0x18001fb9f  jz      short loc_18001FBBD
0x18001fba1  mov     rcx, [rcx+38h]
0x18001fba5  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x18001fbac  mov     edx, 1Fh
0x18001fbb1  mov     [rsp+88h+var_68], edi
0x18001fbb5  mov     r9d, edi
0x18001fbb8  call    WPP_SF_Dd
0x18001fbbd  test    edi, edi
0x18001fbbf  jns     short loc_18001FBD4
0x18001fbc1  cmp     edi, 0C000017Ah
0x18001fbc7  jnz     loc_18001FCC1
0x18001fbcd  xor     edi, edi
0x18001fbcf  jmp     loc_18001FC85
0x18001fbd4  xor     ebp, ebp
0x18001fbd6  cmp     [r15+10h], ebp
0x18001fbda  jbe     loc_18001FC85
0x18001fbe0  mov     r13d, [rsp+88h+arg_0]
0x18001fbe8  mov     r12d, [r15+rbp*4+14h]
0x18001fbed  xor     r8d, r8d
0x18001fbf0  mov     edx, [rbx]
0x18001fbf2  cmp     r8d, edx
0x18001fbf5  jnb     short loc_18001FC06
0x18001fbf7  mov     rax, [rbx+8]
0x18001fbfb  cmp     r12d, [rax+r8*4]
0x18001fbff  jz      short loc_18001FC62
0x18001fc01  inc     r8d
0x18001fc04  jmp     short loc_18001FBF2
0x18001fc06  cmp     edx, r13d
0x18001fc09  jnz     short loc_18001FC56
0x18001fc0b  add     r13d, 0Ah
0x18001fc0f  mov     ecx, 40h ; '@'; uFlags
0x18001fc14  mov     edx, r13d
0x18001fc17  shl     rdx, 2; uBytes
0x18001fc1b  call    cs:__imp_LocalAlloc
0x18001fc21  mov     r15, rax
0x18001fc24  mov     edi, 0C0000017h
0x18001fc29  test    rax, rax
0x18001fc2c  jz      short loc_18001FC70
0x18001fc2e  mov     r8d, [rbx]
0x18001fc31  mov     rcx, rax; void *
0x18001fc34  mov     rdx, [rbx+8]; Src
0x18001fc38  xor     edi, edi
0x18001fc3a  shl     r8, 2; Size
0x18001fc3e  call    memmove_0
0x18001fc43  mov     rcx, [rbx+8]; hMem
0x18001fc47  call    cs:__imp_LocalFree
0x18001fc4d  mov     [rbx+8], r15
0x18001fc51  mov     r15, [rsp+88h+var_58]
0x18001fc56  mov     ecx, [rbx]
0x18001fc58  mov     rax, [rbx+8]
0x18001fc5c  mov     [rax+rcx*4], r12d
0x18001fc60  inc     dword ptr [rbx]
0x18001fc62  inc     ebp
0x18001fc64  cmp     ebp, [r15+10h]
0x18001fc68  jb      loc_18001FBE8
0x18001fc6e  jmp     short loc_18001FC75
0x18001fc70  mov     r15, [rsp+88h+var_58]
0x18001fc75  mov     [rsp+88h+arg_0], r13d
0x18001fc7d  mov     r13, [rsp+88h+arg_8]
0x18001fc85  mov     eax, [rsp+88h+arg_10]
0x18001fc8c  mov     r12d, [rsp+88h+arg_18]
0x18001fc94  inc     eax
0x18001fc96  mov     [rsp+88h+arg_10], eax
0x18001fc9d  cmp     eax, [r13+0]
0x18001fca1  jb      loc_18001FA23
0x18001fca7  jmp     short loc_18001FCC1
0x18001fca9  mov     rcx, [rbx+8]; hMem
0x18001fcad  test    rcx, rcx
0x18001fcb0  jz      short loc_18001FCBC
0x18001fcb2  call    cs:__imp_LocalFree
0x18001fcb8  mov     [rbx+8], rbp
0x18001fcbc  mov     edi, 0C0000017h
0x18001fcc1  test    rsi, rsi
0x18001fcc4  jz      short loc_18001FCD3
0x18001fcc6  mov     rcx, rsi; hMem
0x18001fcc9  call    cs:__imp_LocalFree
0x18001fccf  jmp     short loc_18001FCD3
0x18001fcd1  mov     edi, ebp
0x18001fcd3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcda  mov     r15, [rsp+88h+var_40]
0x18001fcdf  mov     r14, [rsp+88h+var_38]
0x18001fce4  mov     r13, [rsp+88h+var_30]
0x18001fce9  test    dword ptr [rcx+44h], 20000h
0x18001fcf0  mov     r12, [rsp+88h+var_28]
0x18001fcf5  mov     rsi, [rsp+88h+var_20]
0x18001fcfa  mov     rbp, [rsp+88h+var_18]
0x18001fcff  mov     rbx, [rsp+88h+var_10]
0x18001fd04  jz      short loc_18001FD22
0x18001fd06  mov     rcx, [rcx+38h]
0x18001fd0a  lea     r8, WPP_79fcc61a0c813c430ca4f3d6fde880c2_Traceguids
0x18001fd11  mov     edx, 10h
0x18001fd16  mov     [rsp+88h+var_68], edi
0x18001fd1a  mov     r9d, edi
0x18001fd1d  call    WPP_SF_Dd
0x18001fd22  mov     eax, edi
0x18001fd24  add     rsp, 80h
0x18001fd2b  pop     rdi
0x18001fd2c  retn
```
