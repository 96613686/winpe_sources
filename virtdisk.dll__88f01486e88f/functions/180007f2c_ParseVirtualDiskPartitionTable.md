# ParseVirtualDiskPartitionTable

- ea: `0x180007f2c`
- end: `0x1800083bc`
- name: `ParseVirtualDiskPartitionTable`
- size: `1168`
- prototype: `__int64 __fastcall(HANDLE hFile, _DWORD *, _QWORD *, unsigned __int64 *, __int64 *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007378`
- `0x180009b90`

## callees

- `0x180007b7c`
- `0x180007f2c`
- `0x1800085a8`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x180008191`
- `ntdll!RtlComputeCrc32` at `0x18000820b`
- `ntdll!RtlComputeCrc32` at `0x180008191`
- `ntdll!RtlComputeCrc32` at `0x18000820b`
- `ntdll!RtlFreeHeap` at `0x180008395`
- `ntdll!RtlFreeHeap` at `0x180008395`
- `ntdll!RtlAllocateHeap` at `0x180007fdb`
- `ntdll!RtlAllocateHeap` at `0x180007fdb`

## pseudocode

```c
__int64 __fastcall ParseVirtualDiskPartitionTable(
        HANDLE hFile,
        _DWORD *a2,
        _QWORD *a3,
        unsigned __int64 *a4,
        __int64 *a5,
        _QWORD *a6)
{
  __int64 *v6; // r13
  unsigned int VirtualDiskInformationFromDriver; // ebx
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // r15
  char *Heap; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  char *v15; // rdi
  int v16; // r11d
  int v17; // r9d
  int v18; // r10d
  unsigned __int64 v19; // r12
  unsigned int i; // r8d
  __int64 v21; // rdx
  char v22; // al
  int v23; // ecx
  int v24; // eax
  unsigned __int64 v25; // rcx
  char *v26; // rsi
  ULONG v27; // r8d
  int v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // rcx
  unsigned __int64 v31; // rcx
  int v32; // ebx
  ULONG v33; // r13d
  UCHAR *v34; // rbp
  __int64 v35; // r9
  __int64 v36; // r10
  __int64 v37; // r11
  int v38; // ebx
  unsigned int v39; // r8d
  unsigned __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdx
  __int128 v48; // [rsp+38h] [rbp-60h] BYREF
  __int128 v49; // [rsp+48h] [rbp-50h]
  int v51; // [rsp+B0h] [rbp+18h]

  v6 = a5;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v48 = 0;
  *a6 = 0;
  v49 = 0;
  LODWORD(v48) = 1;
  VirtualDiskInformationFromDriver = GetVirtualDiskInformationFromDriver(hFile, 0x20u, &v48, 0, 0);
  if ( !VirtualDiskInformationFromDriver )
  {
    v10 = HIDWORD(v49);
    v11 = *((_QWORD *)&v48 + 1);
    *a3 = *((_QWORD *)&v48 + 1);
    if ( (unsigned int)v10 > 0x10000 )
      return 0;
    Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x20000u);
    v15 = Heap;
    if ( !Heap )
      return 14;
    VirtualDiskInformationFromDriver = ReadRawDataFromVirtualDisk(hFile, v13, v14, Heap);
    if ( VirtualDiskInformationFromDriver )
    {
LABEL_62:
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v15);
      return VirtualDiskInformationFromDriver;
    }
    if ( *((_WORD *)v15 + 255) == 0xAA55
      && (unsigned __int8)(v15[446] - 1) > 0x7Eu
      && (unsigned __int8)(v15[462] - 1) > 0x7Eu
      && (unsigned __int8)(v15[478] - 1) > 0x7Eu
      && (unsigned __int8)(v15[494] - 1) > 0x7Eu )
    {
      v16 = 0;
      v17 = 0;
      v51 = 0;
      v18 = 0;
      v19 = 3145728;
      for ( i = 0; i < 4; ++i )
      {
        v21 = 16LL * i;
        v22 = v15[v21 + 450];
        if ( v22 )
        {
          if ( v22 == 66 )
            goto LABEL_61;
          if ( v22 == -18 )
          {
            v18 = 1;
          }
          else
          {
            v23 = *(_DWORD *)&v15[v21 + 454];
            if ( !v23 || !*(_DWORD *)&v15[v21 + 458] )
              goto LABEL_61;
            v17 = 1;
            if ( v22 == 5 || v22 == 15 )
            {
              v24 = 2;
            }
            else
            {
              *a5 = (unsigned int)(v10 * v23);
              *a6 = (unsigned int)(*(_DWORD *)&v15[v21 + 458] * v10);
              v24 = 1;
            }
            v16 += v24;
            v51 = v16;
            v25 = v10 * (*(unsigned int *)&v15[v21 + 454] + (unsigned __int64)*(unsigned int *)&v15[v21 + 458]);
            if ( v25 + 0x100000 >= v25 && v25 + 0x100000 <= v11 )
              v25 += 0x100000LL;
            if ( v25 <= v19 )
              v25 = v19;
            v19 = v25;
          }
        }
      }
      if ( !v18 )
        goto LABEL_58;
      if ( !v17 )
      {
        v26 = &v15[v10];
        if ( *(_QWORD *)&v15[v10] == 0x5452415020494645LL )
        {
          v27 = *((_DWORD *)v26 + 3);
          if ( v27 <= (unsigned int)v10 )
          {
            v28 = *((_DWORD *)v26 + 4);
            *((_DWORD *)v26 + 4) = 0;
            if ( RtlComputeCrc32(0, (PUCHAR)&v15[v10], v27) == v28 )
            {
              v29 = *((unsigned int *)v26 + 20);
              *((_DWORD *)v26 + 4) = v28;
              if ( (unsigned int)(v29 - 1) <= 0x4FF )
              {
                v30 = *((unsigned int *)v26 + 21);
                if ( (unsigned int)(v30 - 48) <= 0x4D0 )
                {
                  v31 = v29 * v30;
                  if ( v31 <= 0xFFFFFFFF && 2 * (0x10000 - (int)v10) >= (unsigned int)v31 )
                  {
                    v32 = *((_DWORD *)v26 + 22);
                    v33 = ~(v10 - 1) & (v31 + v10 - 1);
                    v34 = (UCHAR *)&v15[(unsigned int)(2 * v10)];
                    if ( RtlComputeCrc32(0, v34, v33) == v32 )
                    {
                      v35 = *(_QWORD *)PARTITION_ENTRY_UNUSED_GUID.Data4;
                      v36 = *(_QWORD *)PARTITION_LDM_METADATA_GUID.Data4;
                      v37 = *(_QWORD *)&PARTITION_LDM_METADATA_GUID.Data1;
                      v38 = v51;
                      v39 = 0;
                      v40 = (~(unsigned __int64)v33 - v10) / v10;
                      while ( v39 < *((_DWORD *)v26 + 20) )
                      {
                        v41 = *((_DWORD *)v26 + 21) * v39;
                        v42 = *(_QWORD *)&v34[v41] - *(_QWORD *)&PARTITION_ENTRY_UNUSED_GUID.Data1;
                        if ( !v42 )
                          v42 = *(_QWORD *)&v34[v41 + 8] - v35;
                        if ( v42 )
                        {
                          v43 = *(_QWORD *)&v34[v41] - v37;
                          if ( !v43 )
                            v43 = *(_QWORD *)&v34[v41 + 8] - v36;
                          if ( !v43 || *(_QWORD *)&v34[v41 + 40] >= v40 )
                            goto LABEL_61;
                          v44 = *(_QWORD *)&v34[v41] - *(_QWORD *)&PARTITION_BASIC_DATA_GUID.Data1;
                          if ( !v44 )
                            v44 = *(_QWORD *)&v34[v41 + 8] - *(_QWORD *)PARTITION_BASIC_DATA_GUID.Data4;
                          if ( !v44 )
                          {
                            v51 = ++v38;
                            v45 = *(_QWORD *)&v34[v41 + 32] * v10;
                            *a5 = v45;
                            *a6 = v10 * (*(_QWORD *)&v34[v41 + 40] + 1LL) - v45;
                            v35 = *(_QWORD *)PARTITION_ENTRY_UNUSED_GUID.Data4;
                            v36 = *(_QWORD *)PARTITION_LDM_METADATA_GUID.Data4;
                            v37 = *(_QWORD *)&PARTITION_LDM_METADATA_GUID.Data1;
                          }
                          v40 = (~(unsigned __int64)v33 - v10) / v10;
                          v46 = v10 * (*(_QWORD *)&v34[v41 + 40] + 1LL);
                          if ( v46 + (unsigned __int64)((unsigned int)v10 + v33) > v19 )
                            v19 = v46 + (unsigned int)v10 + v33;
                        }
                        ++v39;
                      }
                      v16 = v51;
                      v6 = a5;
LABEL_58:
                      if ( v16 != 1 )
                      {
                        *v6 = 0;
                        *a6 = 0;
                      }
                      *a2 = 1;
                      *a4 = v19;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_61:
    VirtualDiskInformationFromDriver = 0;
    goto LABEL_62;
  }
  return VirtualDiskInformationFromDriver;
}

```

## disassembly

```asm
0x180007f2c  mov     r11, rsp
0x180007f2f  mov     [r11+8], rbx
0x180007f33  mov     [r11+20h], r9
0x180007f37  mov     [r11+10h], rdx
0x180007f3b  push    rbp
0x180007f3c  push    rsi
0x180007f3d  push    rdi
0x180007f3e  push    r12
0x180007f40  push    r13
0x180007f42  push    r14
0x180007f44  push    r15
0x180007f46  sub     rsp, 60h
0x180007f4a  mov     rax, [rsp+98h+arg_28]
0x180007f52  xor     r12d, r12d
0x180007f55  mov     r13, [rsp+98h+arg_20]
0x180007f5d  xorps   xmm0, xmm0
0x180007f60  mov     rdi, r8
0x180007f63  mov     [rdx], r12d
0x180007f66  mov     [r8], r12
0x180007f69  mov     rsi, rcx
0x180007f6c  mov     [r9], r12
0x180007f6f  lea     edx, [r12+20h]
0x180007f74  mov     [r13+0], r12
0x180007f78  lea     r8, [r11-60h]
0x180007f7c  movups  [rsp+98h+var_60], xmm0
0x180007f81  xor     r9d, r9d
0x180007f84  mov     [rax], r12
0x180007f87  movups  [rsp+98h+var_50], xmm0
0x180007f8c  mov     dword ptr [rsp+98h+var_60], 1
0x180007f94  mov     [r11-78h], r12
0x180007f98  call    GetVirtualDiskInformationFromDriver
0x180007f9d  mov     ebx, eax
0x180007f9f  test    eax, eax
0x180007fa1  jnz     loc_1800083A1
0x180007fa7  mov     r14d, dword ptr [rsp+98h+var_50+0Ch]
0x180007fac  mov     ebp, 10000h
0x180007fb1  mov     r15, qword ptr [rsp+98h+var_60+8]
0x180007fb6  mov     [rdi], r15
0x180007fb9  cmp     r14d, ebp
0x180007fbc  jbe     short loc_180007FC6
0x180007fbe  mov     ebx, r12d
0x180007fc1  jmp     loc_1800083A1
0x180007fc6  mov     rcx, gs:60h
0x180007fcf  xor     edx, edx; Flags
0x180007fd1  mov     r8d, 20000h; Size
0x180007fd7  mov     rcx, [rcx+30h]; HeapHandle
0x180007fdb  call    cs:__imp_RtlAllocateHeap
0x180007fe2  nop     dword ptr [rax+rax+00h]
0x180007fe7  mov     rdi, rax
0x180007fea  test    rax, rax
0x180007fed  jnz     short loc_180007FF7
0x180007fef  lea     ebx, [rax+0Eh]
0x180007ff2  jmp     loc_1800083A1
0x180007ff7  mov     r9, rdi
0x180007ffa  mov     rcx, rsi; hFile
0x180007ffd  call    ReadRawDataFromVirtualDisk
0x180008002  mov     ebx, eax
0x180008004  test    eax, eax
0x180008006  jnz     loc_180008383
0x18000800c  mov     eax, 0AA55h
0x180008011  cmp     [rdi+1FEh], ax
0x180008018  jnz     loc_180008381
0x18000801e  mov     al, [rdi+1BEh]
0x180008024  mov     cl, 7Eh ; '~'
0x180008026  dec     al
0x180008028  cmp     al, cl
0x18000802a  jbe     loc_180008381
0x180008030  mov     al, [rdi+1CEh]
0x180008036  dec     al
0x180008038  cmp     al, cl
0x18000803a  jbe     loc_180008381
0x180008040  mov     al, [rdi+1DEh]
0x180008046  dec     al
0x180008048  cmp     al, cl
0x18000804a  jbe     loc_180008381
0x180008050  mov     al, [rdi+1EEh]
0x180008056  dec     al
0x180008058  cmp     al, cl
0x18000805a  jbe     loc_180008381
0x180008060  mov     rbx, [rsp+98h+arg_28]
0x180008068  xor     r11d, r11d
0x18000806b  xor     r9d, r9d
0x18000806e  mov     [rsp+98h+arg_10], r11d
0x180008076  xor     r10d, r10d
0x180008079  mov     r12d, 300000h
0x18000807f  xor     r8d, r8d
0x180008082  cmp     r8d, 4
0x180008086  jnb     loc_18000814C
0x18000808c  mov     edx, r8d
0x18000808f  shl     rdx, 4
0x180008093  mov     al, [rdx+rdi+1C2h]
0x18000809a  test    al, al
0x18000809c  jz      loc_180008144
0x1800080a2  cmp     al, 42h ; 'B'
0x1800080a4  jz      loc_180008381
0x1800080aa  cmp     al, 0EEh
0x1800080ac  jz      loc_18000813E
0x1800080b2  mov     ecx, [rdx+rdi+1C6h]
0x1800080b9  test    ecx, ecx
0x1800080bb  jz      loc_180008381
0x1800080c1  cmp     dword ptr [rdx+rdi+1CAh], 0
0x1800080c9  jz      loc_180008381
0x1800080cf  mov     r9d, 1
0x1800080d5  cmp     al, 5
0x1800080d7  jz      short loc_1800080FA
0x1800080d9  cmp     al, 0Fh
0x1800080db  jz      short loc_1800080FA
0x1800080dd  imul    ecx, r14d
0x1800080e1  mov     eax, ecx
0x1800080e3  mov     [r13+0], rax
0x1800080e7  mov     eax, r14d
0x1800080ea  imul    eax, [rdx+rdi+1CAh]
0x1800080f2  mov     [rbx], rax
0x1800080f5  mov     eax, r9d
0x1800080f8  jmp     short loc_1800080FF
0x1800080fa  mov     eax, 2
0x1800080ff  mov     ecx, [rdx+rdi+1CAh]
0x180008106  add     r11d, eax
0x180008109  mov     eax, [rdx+rdi+1C6h]
0x180008110  add     rcx, rax
0x180008113  mov     [rsp+98h+arg_10], r11d
0x18000811b  imul    rcx, r14
0x18000811f  lea     rax, [rcx+100000h]
0x180008126  cmp     rax, rcx
0x180008129  jbe     short loc_180008132
0x18000812b  cmp     rax, r15
0x18000812e  cmovbe  rcx, rax
0x180008132  cmp     rcx, r12
0x180008135  cmovbe  rcx, r12
0x180008139  mov     r12, rcx
0x18000813c  jmp     short loc_180008144
0x18000813e  mov     r10d, 1
0x180008144  inc     r8d
0x180008147  jmp     loc_180008082
0x18000814c  test    r10d, r10d
0x18000814f  jz      loc_18000834B
0x180008155  test    r9d, r9d
0x180008158  jnz     loc_180008381
0x18000815e  lea     rsi, [r14+rdi]
0x180008162  mov     rcx, 5452415020494645h
0x18000816c  mov     r15, r14
0x18000816f  cmp     [rsi], rcx
0x180008172  jnz     loc_180008381
0x180008178  mov     r8d, [rsi+0Ch]; Length
0x18000817c  cmp     r8d, r14d
0x18000817f  ja      loc_180008381
0x180008185  mov     ebx, [rsi+10h]
0x180008188  mov     rdx, rsi; Buffer
0x18000818b  xor     ecx, ecx; InitialCrc
0x18000818d  mov     [rsi+10h], r9d
0x180008191  call    cs:__imp_RtlComputeCrc32
0x180008198  nop     dword ptr [rax+rax+00h]
0x18000819d  cmp     eax, ebx
0x18000819f  jnz     loc_180008381
0x1800081a5  mov     edx, [rsi+50h]
0x1800081a8  mov     [rsi+10h], ebx
0x1800081ab  lea     eax, [rdx-1]
0x1800081ae  cmp     eax, 4FFh
0x1800081b3  ja      loc_180008381
0x1800081b9  mov     ecx, [rsi+54h]
0x1800081bc  lea     eax, [rcx-30h]
0x1800081bf  cmp     eax, 4D0h
0x1800081c4  ja      loc_180008381
0x1800081ca  imul    rcx, rdx
0x1800081ce  mov     eax, 0FFFFFFFFh
0x1800081d3  cmp     rcx, rax
0x1800081d6  ja      loc_180008381
0x1800081dc  sub     ebp, r14d
0x1800081df  add     ebp, ebp
0x1800081e1  cmp     ebp, ecx
0x1800081e3  jb      loc_180008381
0x1800081e9  mov     ebx, [rsi+58h]
0x1800081ec  lea     eax, [r14-1]
0x1800081f0  not     eax
0x1800081f2  lea     r13d, [r14-1]
0x1800081f6  add     r13d, ecx
0x1800081f9  lea     ebp, [r14+r14]
0x1800081fd  and     r13d, eax
0x180008200  add     rbp, rdi
0x180008203  mov     r8d, r13d; Length
0x180008206  mov     rdx, rbp; Buffer
0x180008209  xor     ecx, ecx; InitialCrc
0x18000820b  call    cs:__imp_RtlComputeCrc32
0x180008212  nop     dword ptr [rax+rax+00h]
0x180008217  cmp     eax, ebx
0x180008219  jnz     loc_180008381
0x18000821f  mov     r9, qword ptr cs:PARTITION_ENTRY_UNUSED_GUID.Data4
0x180008226  xor     edx, edx
0x180008228  mov     r10, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data4
0x18000822f  mov     r11, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data1
0x180008236  mov     ebx, [rsp+98h+arg_10]
0x18000823d  mov     eax, r13d
0x180008240  not     rax
0x180008243  sub     rax, r14
0x180008246  div     r15
0x180008249  xor     r8d, r8d
0x18000824c  mov     rcx, rax
0x18000824f  mov     [rsp+98h+var_68], rax
0x180008254  cmp     r8d, [rsi+50h]
0x180008258  jnb     loc_18000833B
0x18000825e  mov     eax, r8d
0x180008261  imul    eax, [rsi+54h]
0x180008265  mov     edx, eax
0x180008267  mov     rax, [rax+rbp]
0x18000826b  sub     rax, qword ptr cs:PARTITION_ENTRY_UNUSED_GUID.Data1
0x180008272  jnz     short loc_18000827C
0x180008274  mov     rax, [rdx+rbp+8]
0x180008279  sub     rax, r9
0x18000827c  test    rax, rax
0x18000827f  jz      loc_180008333
0x180008285  mov     rax, [rdx+rbp]
0x180008289  sub     rax, r11
0x18000828c  jnz     short loc_180008296
0x18000828e  mov     rax, [rdx+rbp+8]
0x180008293  sub     rax, r10
0x180008296  test    rax, rax
0x180008299  jz      loc_180008381
0x18000829f  cmp     [rdx+rbp+28h], rcx
0x1800082a4  jnb     loc_180008381
0x1800082aa  mov     rax, [rdx+rbp]
0x1800082ae  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data1
0x1800082b5  jnz     short loc_1800082C3
0x1800082b7  mov     rax, [rdx+rbp+8]
0x1800082bc  sub     rax, qword ptr cs:PARTITION_BASIC_DATA_GUID.Data4
0x1800082c3  test    rax, rax
0x1800082c6  jnz     short loc_180008314
0x1800082c8  mov     rax, [rsp+98h+arg_20]
0x1800082d0  inc     ebx
0x1800082d2  mov     rcx, r15
0x1800082d5  mov     [rsp+98h+arg_10], ebx
0x1800082dc  imul    rcx, [rdx+rbp+20h]
0x1800082e2  mov     [rax], rcx
0x1800082e5  mov     rax, [rdx+rbp+28h]
0x1800082ea  inc     rax
0x1800082ed  imul    rax, r15
0x1800082f1  sub     rax, rcx
0x1800082f4  mov     rcx, [rsp+98h+arg_28]
0x1800082fc  mov     [rcx], rax
0x1800082ff  mov     r9, qword ptr cs:PARTITION_ENTRY_UNUSED_GUID.Data4
0x180008306  mov     r10, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data4
0x18000830d  mov     r11, qword ptr cs:PARTITION_LDM_METADATA_GUID.Data1
0x180008314  mov     rdx, [rdx+rbp+28h]
0x180008319  lea     eax, [r14+r13]
0x18000831d  mov     rcx, [rsp+98h+var_68]
0x180008322  inc     rdx
0x180008325  imul    rdx, r15
0x180008329  add     rax, rdx
0x18000832c  cmp     rax, r12
0x18000832f  cmova   r12, rax
0x180008333  inc     r8d
0x180008336  jmp     loc_180008254
0x18000833b  mov     r11d, [rsp+98h+arg_10]
0x180008343  mov     r13, [rsp+98h+arg_20]
0x18000834b  cmp     r11d, 1
0x18000834f  jz      short loc_180008368
0x180008351  mov     rax, [rsp+98h+arg_28]
0x180008359  mov     qword ptr [r13+0], 0
0x180008361  mov     qword ptr [rax], 0
0x180008368  mov     rax, [rsp+98h+arg_8]
0x180008370  mov     dword ptr [rax], 1
0x180008376  mov     rax, [rsp+98h+arg_18]
0x18000837e  mov     [rax], r12
0x180008381  xor     ebx, ebx
0x180008383  mov     rcx, gs:60h
0x18000838c  mov     r8, rdi; P
0x18000838f  xor     edx, edx; Flags
0x180008391  mov     rcx, [rcx+30h]; HeapHandle
0x180008395  call    cs:__imp_RtlFreeHeap
0x18000839c  nop     dword ptr [rax+rax+00h]
0x1800083a1  mov     eax, ebx
0x1800083a3  mov     rbx, [rsp+98h+arg_0]
0x1800083ab  add     rsp, 60h
0x1800083af  pop     r15
0x1800083b1  pop     r14
0x1800083b3  pop     r13
0x1800083b5  pop     r12
0x1800083b7  pop     rdi
0x1800083b8  pop     rsi
0x1800083b9  pop     rbp
0x1800083ba  retn
```
