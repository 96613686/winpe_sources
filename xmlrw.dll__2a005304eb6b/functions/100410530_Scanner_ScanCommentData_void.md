# Scanner::ScanCommentData(void)

- ea: `0x100410530`
- end: `0x10041073d`
- name: `?ScanCommentData@Scanner@@AEAAXXZ`
- size: `525`
- prototype: `void __fastcall(Scanner *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x100401780`
- `0x10040f530`
- `0x100410530`
- `0x100439df0`

## pseudocode

```c
void __fastcall Scanner::ScanCommentData(Scanner *this)
{
  __int64 v2; // rcx
  __int16 v3; // ax
  __int64 v4; // rdx
  __int16 v5; // ax
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  _DWORD *v11; // rcx
  int v12; // eax
  int v13; // ecx

  *((_DWORD *)this + 68) = 0;
  v2 = *((_QWORD *)this + 8);
  *(_QWORD *)(v2 + 56) = *(_QWORD *)(v2 + 48);
  *(_DWORD *)(v2 + 88) = 1;
  v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
  *((_DWORD *)this + 18) = 7;
  while ( 1 )
  {
    --*((_DWORD *)this + 67);
    *((_WORD *)this + 92) = v3;
    if ( v3 == 10 )
    {
      v9 = *((_QWORD *)this + 8);
      v10 = *(_QWORD *)(v9 + 48);
      ++*(_DWORD *)(v9 + 104);
      *(_QWORD *)(v9 + 96) = v10;
      goto LABEL_15;
    }
    if ( v3 == 13 )
    {
      v6 = *((_QWORD *)this + 8);
      LOBYTE(v4) = 10;
      v7 = *(_QWORD *)(v6 + 48);
      ++*(_DWORD *)(v6 + 104);
      *(_QWORD *)(v6 + 96) = v7;
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 8) + 128LL))(*((_QWORD *)this + 8), v4);
      LOBYTE(v8) = 10;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 8) + 120LL))(
             *((_QWORD *)this + 8),
             v8) )
      {
        *(_QWORD *)(*((_QWORD *)this + 8) + 96LL) = *(_QWORD *)(*((_QWORD *)this + 8) + 48LL);
        return;
      }
      goto LABEL_15;
    }
    if ( v3 == 45 )
      break;
    if ( (unsigned __int16)(v3 + 2) <= 0x21u )
    {
      _mm_lfence();
      if ( (*((_BYTE *)g_apCharTables + (unsigned __int8)v3) & 0x20) == 0 )
      {
        if ( !*(_BYTE *)(*((_QWORD *)this + 8) + 24LL) )
        {
          MXRRaiseException(-1072894421);
          JUMPOUT(0x10041073CLL);
        }
        Scanner::CheckEndOfInput(this);
        return;
      }
    }
LABEL_15:
    v11 = (_DWORD *)*((_QWORD *)this + 8);
    if ( *((int *)this + 67) <= 0 )
    {
      *((_DWORD *)this + 68) = 1;
      --v11[22];
      return;
    }
    v3 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 88LL))(v11);
  }
  LOBYTE(v4) = 45;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 8) + 120LL))(
          *((_QWORD *)this + 8),
          v4) )
    goto LABEL_15;
  v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 88LL))(*((_QWORD *)this + 8));
  *((_WORD *)this + 92) = v5;
  if ( v5 != 62 )
  {
    MXRRaiseException(-1072894429);
    __debugbreak();
  }
  *(_DWORD *)(*((_QWORD *)this + 8) + 88LL) += 2;
  v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 8) + 96LL))(*((_QWORD *)this + 8));
  if ( v12 || *((int *)this + 18) >= 15 )
  {
    *((_QWORD *)this + 22) = Scanner::ScanCommentEnd;
  }
  else
  {
    v13 = --*((_DWORD *)this + 26);
    *((_DWORD *)this + 18) = 16;
    *((_QWORD *)this + 22) = *(_QWORD *)(*((_QWORD *)this + 12) + 8LL * (unsigned int)(v13 - 1));
  }
}

```

## disassembly

```asm
0x100410530  mov     [rsp+arg_0], rbx
0x100410535  push    rdi
0x100410536  sub     rsp, 20h
0x10041053a  mov     dword ptr [rcx+110h], 0
0x100410544  mov     rbx, rcx
0x100410547  mov     rcx, [rcx+40h]
0x10041054b  mov     rax, [rcx+30h]
0x10041054f  mov     [rcx+38h], rax
0x100410553  mov     dword ptr [rcx+58h], 1
0x10041055a  mov     rcx, [rbx+40h]
0x10041055e  mov     rax, [rcx]
0x100410561  mov     rax, [rax+58h]
0x100410565  call    cs:__guard_dispatch_icall_fptr
0x10041056b  mov     dword ptr [rbx+48h], 7
0x100410572  lea     rdi, ?g_apCharTables@@3PAPEAEA; uchar * near * g_apCharTables
0x100410579  dec     dword ptr [rbx+10Ch]
0x10041057f  movzx   ecx, ax
0x100410582  mov     [rbx+0B8h], ax
0x100410589  cmp     ecx, 0Ah
0x10041058c  jz      loc_10041067C
0x100410592  cmp     ecx, 0Dh
0x100410595  jz      loc_100410629
0x10041059b  cmp     ecx, 2Dh ; '-'
0x10041059e  jz      short loc_1004105E7
0x1004105a0  lea     eax, [rcx+2]
0x1004105a3  cmp     ax, 21h ; '!'
0x1004105a7  ja      loc_10041068B
0x1004105ad  lfence
0x1004105b0  mov     eax, ecx
0x1004105b2  movzx   ecx, cl
0x1004105b5  shr     rax, 8
0x1004105b9  mov     rax, [rdi+rax*8]
0x1004105bd  test    byte ptr [rcx+rax], 20h
0x1004105c1  jnz     loc_10041068B
0x1004105c7  mov     rax, [rbx+40h]
0x1004105cb  cmp     byte ptr [rax+18h], 0
0x1004105cf  jz      loc_100410732
0x1004105d5  mov     rcx, rbx; this
0x1004105d8  mov     rbx, [rsp+28h+arg_0]
0x1004105dd  add     rsp, 20h
0x1004105e1  pop     rdi
0x1004105e2  jmp     ?CheckEndOfInput@Scanner@@AEAAXXZ; Scanner::CheckEndOfInput(void)
0x1004105e7  mov     rcx, [rbx+40h]
0x1004105eb  mov     dl, 2Dh ; '-'
0x1004105ed  mov     rax, [rcx]
0x1004105f0  mov     rax, [rax+78h]
0x1004105f4  call    cs:__guard_dispatch_icall_fptr
0x1004105fa  test    al, al
0x1004105fc  jz      loc_10041068B
0x100410602  mov     rcx, [rbx+40h]
0x100410606  mov     rax, [rcx]
0x100410609  mov     rax, [rax+58h]
0x10041060d  call    cs:__guard_dispatch_icall_fptr
0x100410613  mov     [rbx+0B8h], ax
0x10041061a  cmp     ax, 3Eh ; '>'
0x10041061e  jnz     loc_100410727
0x100410624  jmp     loc_1004106AA
0x100410629  mov     rcx, [rbx+40h]
0x10041062d  mov     dl, 0Ah
0x10041062f  mov     rax, [rcx+30h]
0x100410633  inc     dword ptr [rcx+68h]
0x100410636  mov     [rcx+60h], rax
0x10041063a  mov     rcx, [rbx+40h]
0x10041063e  mov     rax, [rcx]
0x100410641  mov     rax, [rax+80h]
0x100410648  call    cs:__guard_dispatch_icall_fptr
0x10041064e  mov     rcx, [rbx+40h]
0x100410652  mov     dl, 0Ah
0x100410654  mov     rax, [rcx]
0x100410657  mov     rax, [rax+78h]
0x10041065b  call    cs:__guard_dispatch_icall_fptr
0x100410661  test    al, al
0x100410663  jz      short loc_10041068B
0x100410665  mov     rcx, [rbx+40h]
0x100410669  mov     rax, [rcx+30h]
0x10041066d  mov     [rcx+60h], rax
0x100410671  mov     rbx, [rsp+28h+arg_0]
0x100410676  add     rsp, 20h
0x10041067a  pop     rdi
0x10041067b  retn
0x10041067c  mov     rcx, [rbx+40h]
0x100410680  mov     rax, [rcx+30h]
0x100410684  inc     dword ptr [rcx+68h]
0x100410687  mov     [rcx+60h], rax
0x10041068b  cmp     dword ptr [rbx+10Ch], 0
0x100410692  mov     rcx, [rbx+40h]
0x100410696  jle     short loc_10041070F
0x100410698  mov     rax, [rcx]
0x10041069b  mov     rax, [rax+58h]
0x10041069f  call    cs:__guard_dispatch_icall_fptr
0x1004106a5  jmp     loc_100410579
0x1004106aa  mov     rax, [rbx+40h]
0x1004106ae  add     dword ptr [rax+58h], 2
0x1004106b2  mov     rcx, [rbx+40h]
0x1004106b6  mov     rax, [rcx]
0x1004106b9  mov     rax, [rax+60h]
0x1004106bd  call    cs:__guard_dispatch_icall_fptr
0x1004106c3  test    eax, eax
0x1004106c5  jnz     short loc_1004106F6
0x1004106c7  cmp     dword ptr [rbx+48h], 0Fh
0x1004106cb  jge     short loc_1004106F6
0x1004106cd  dec     dword ptr [rbx+68h]
0x1004106d0  mov     ecx, [rbx+68h]
0x1004106d3  mov     dword ptr [rbx+48h], 10h
0x1004106da  dec     ecx
0x1004106dc  mov     rax, [rbx+60h]
0x1004106e0  mov     rdx, [rax+rcx*8]
0x1004106e4  mov     [rbx+0B0h], rdx
0x1004106eb  mov     rbx, [rsp+28h+arg_0]
0x1004106f0  add     rsp, 20h
0x1004106f4  pop     rdi
0x1004106f5  retn
0x1004106f6  lea     rdx, ?ScanCommentEnd@Scanner@@AEAAXXZ; Scanner::ScanCommentEnd(void)
0x1004106fd  mov     [rbx+0B0h], rdx
0x100410704  mov     rbx, [rsp+28h+arg_0]
0x100410709  add     rsp, 20h
0x10041070d  pop     rdi
0x10041070e  retn
0x10041070f  mov     dword ptr [rbx+110h], 1
0x100410719  dec     dword ptr [rcx+58h]
0x10041071c  mov     rbx, [rsp+28h+arg_0]
0x100410721  add     rsp, 20h
0x100410725  pop     rdi
0x100410726  retn
0x100410727  mov     ecx, 0C00CEE23h; int
0x10041072c  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100410731  int     3; Trap to Debugger
0x100410732  mov     ecx, 0C00CEE2Bh; int
0x100410737  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
