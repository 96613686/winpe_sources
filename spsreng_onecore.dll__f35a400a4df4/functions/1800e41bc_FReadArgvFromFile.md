# FReadArgvFromFile

- ea: `0x1800e41bc`
- end: `0x1800e4287`
- name: `FReadArgvFromFile`
- size: `203`
- prototype: `__int64 __fastcall(FILE *Stream)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180061a90`

## callees

- `0x1800022d0`
- `0x180002470`
- `0x180002aac`
- `0x1800e41bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800e4270`
- `api-ms-win-crt-private-l1-1-0!_o_fclose` at `0x1800e4270`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800e423a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800e423a`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800e41e8`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800e4206`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800e41e8`
- `api-ms-win-crt-private-l1-1-0!_o_fseek` at `0x1800e4206`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x1800e41f5`
- `api-ms-win-crt-private-l1-1-0!_o_ftell` at `0x1800e41f5`

## pseudocode

```c
__int64 __fastcall FReadArgvFromFile(FILE *Stream, __int64 a2, __int64 a3, _QWORD *a4)
{
  unsigned int v4; // esi
  size_t v9; // rdi
  size_t v10; // r14
  _BYTE *v11; // rax
  _BYTE *v12; // rdi

  v4 = 0;
  if ( Stream )
  {
    if ( !fseek(Stream, 0, 2) )
    {
      v9 = (int)_o_ftell(Stream);
      if ( !fseek(Stream, 0, 0) )
      {
        v10 = v9;
        v11 = CWinHeap::Alloc((CWinHeap *)&g_heap, v9 + 1, 1);
        v12 = v11;
        if ( v11 )
        {
          if ( fread(v11, 1u, v10, Stream) == v10 )
          {
            v12[v10] = 0;
            *a4 = v12;
            v4 = FSzCmdLineToArgv(a2, a3, v12);
          }
          else
          {
            CWinHeap::Free((CWinHeap *)&g_heap, v12);
          }
        }
      }
    }
    fclose(Stream);
  }
  return v4;
}

```

## disassembly

```asm
0x1800e41bc  push    rbx
0x1800e41be  push    rbp
0x1800e41bf  push    rsi
0x1800e41c0  push    rdi
0x1800e41c1  push    r12
0x1800e41c3  push    r14
0x1800e41c5  push    r15
0x1800e41c7  sub     rsp, 20h
0x1800e41cb  xor     esi, esi
0x1800e41cd  mov     r15, r9
0x1800e41d0  mov     rbp, r8
0x1800e41d3  mov     r12, rdx
0x1800e41d6  mov     rbx, rcx
0x1800e41d9  test    rcx, rcx
0x1800e41dc  jz      loc_1800E4276
0x1800e41e2  xor     edx, edx; Offset
0x1800e41e4  lea     r8d, [rsi+2]; Origin
0x1800e41e8  call    cs:__imp_fseek
0x1800e41ee  test    eax, eax
0x1800e41f0  jnz     short loc_1800E426D
0x1800e41f2  mov     rcx, rbx
0x1800e41f5  call    cs:__imp__o_ftell
0x1800e41fb  xor     r8d, r8d; Origin
0x1800e41fe  xor     edx, edx; Offset
0x1800e4200  mov     rcx, rbx; Stream
0x1800e4203  movsxd  rdi, eax
0x1800e4206  call    cs:__imp_fseek
0x1800e420c  test    eax, eax
0x1800e420e  jnz     short loc_1800E426D
0x1800e4210  lea     rdx, [rdi+1]; unsigned __int64
0x1800e4214  mov     r8b, 1; bool
0x1800e4217  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800e421e  mov     r14, rdi
0x1800e4221  call    ?Alloc@CWinHeap@@QEAAPEAX_K_N@Z; CWinHeap::Alloc(unsigned __int64,bool)
0x1800e4226  mov     rdi, rax
0x1800e4229  test    rax, rax
0x1800e422c  jz      short loc_1800E426D
0x1800e422e  mov     r9, rbx; Stream
0x1800e4231  lea     edx, [rsi+1]; ElementSize
0x1800e4234  mov     r8, r14; ElementCount
0x1800e4237  mov     rcx, rax; Buffer
0x1800e423a  call    cs:__imp_fread
0x1800e4240  cmp     rax, r14
0x1800e4243  jnz     short loc_1800E425E
0x1800e4245  mov     [r14+rdi], sil
0x1800e4249  mov     r8, rdi
0x1800e424c  mov     rdx, rbp
0x1800e424f  mov     [r15], rdi
0x1800e4252  mov     rcx, r12
0x1800e4255  call    FSzCmdLineToArgv
0x1800e425a  mov     esi, eax
0x1800e425c  jmp     short loc_1800E426D
0x1800e425e  mov     rdx, rdi; void *
0x1800e4261  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x1800e4268  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x1800e426d  mov     rcx, rbx; Stream
0x1800e4270  call    cs:__imp_fclose
0x1800e4276  mov     eax, esi
0x1800e4278  add     rsp, 20h
0x1800e427c  pop     r15
0x1800e427e  pop     r14
0x1800e4280  pop     r12
0x1800e4282  pop     rdi
0x1800e4283  pop     rsi
0x1800e4284  pop     rbp
0x1800e4285  pop     rbx
0x1800e4286  retn
```
