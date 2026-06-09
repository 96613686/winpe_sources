# UpdateLastAccessTimesMap(_FILE_ID_EXTD_DIR_INFORMATION *,uchar,std::map<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>> *)

- ea: `0x18001d6c0`
- end: `0x18001d8a5`
- name: `?UpdateLastAccessTimesMap@@YAXPEAU_FILE_ID_EXTD_DIR_INFORMATION@@EPEAV?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@@Z`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001ad40`
- `0x18001d8b0`

## callees

- `0x180017dc8`
- `0x18001d6c0`
- `0x18001f458`

## pseudocode

```c
void __fastcall UpdateLastAccessTimesMap(union _LARGE_INTEGER *a1, char a2, __int64 a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  union _LARGE_INTEGER v15; // rbx
  _QWORD *v16; // rax
  int v17; // [rsp+50h] [rbp+28h] BYREF

  if ( a1[6].QuadPart )
  {
    if ( a2 )
    {
      if ( CompareTimeThreshold(a1[2], 0x21C0u) == -1 )
      {
        v17 = 39;
        v6 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
        ++*v6;
        v17 = 40;
LABEL_21:
        v15 = a1[5];
        v16 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
        *v16 += v15.QuadPart;
        return;
      }
      if ( a2 && CompareTimeThreshold(a1[2], 0x10E0u) == -1 )
      {
        v17 = 37;
        v7 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
        ++*v7;
        v17 = 38;
        goto LABEL_21;
      }
    }
    if ( CompareTimeThreshold(a1[2], 0x870u) == -1 )
    {
      if ( a2 )
      {
        v17 = 35;
        v8 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
        ++*v8;
        v17 = 36;
      }
      else
      {
        v17 = 33;
        v9 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
        ++*v9;
        v17 = 34;
      }
    }
    else if ( CompareTimeThreshold(a1[2], 0x5A0u) == -1 )
    {
      v17 = 31;
      v10 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
      ++*v10;
      v17 = 32;
    }
    else if ( CompareTimeThreshold(a1[2], 0x2D0u) == -1 )
    {
      v17 = 29;
      v11 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
      ++*v11;
      v17 = 30;
    }
    else if ( CompareTimeThreshold(a1[2], 0x150u) == -1 )
    {
      v17 = 27;
      v12 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
      ++*v12;
      v17 = 28;
    }
    else if ( CompareTimeThreshold(a1[2], 0xA8u) == -1 )
    {
      v17 = 25;
      v13 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
      ++*v13;
      v17 = 26;
    }
    else
    {
      v17 = 23;
      v14 = (_QWORD *)std::map<unsigned long,unsigned __int64>::operator[](a3, &v17);
      ++*v14;
      v17 = 24;
    }
    goto LABEL_21;
  }
}

```

## disassembly

```asm
0x18001d6c0  push    rbp
0x18001d6c2  push    rbx
0x18001d6c3  push    rsi
0x18001d6c4  push    rdi
0x18001d6c5  mov     rbp, rsp
0x18001d6c8  sub     rsp, 28h
0x18001d6cc  cmp     qword ptr [rcx+30h], 0
0x18001d6d1  mov     rdi, r8
0x18001d6d4  mov     sil, dl
0x18001d6d7  mov     rbx, rcx
0x18001d6da  jz      loc_18001D89C
0x18001d6e0  test    dl, dl
0x18001d6e2  jz      short loc_18001D753
0x18001d6e4  mov     rcx, [rcx+10h]; union _LARGE_INTEGER
0x18001d6e8  mov     edx, 21C0h; unsigned int
0x18001d6ed  call    ?CompareTimeThreshold@@YAJT_LARGE_INTEGER@@K@Z; CompareTimeThreshold(_LARGE_INTEGER,ulong)
0x18001d6f2  cmp     eax, 0FFFFFFFFh
0x18001d6f5  jnz     short loc_18001D719
0x18001d6f7  lea     rdx, [rbp+arg_0]
0x18001d6fb  mov     [rbp+arg_0], 27h ; '''
0x18001d702  mov     rcx, rdi
0x18001d705  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d70a  inc     qword ptr [rax]
0x18001d70d  mov     [rbp+arg_0], 28h ; '('
0x18001d714  jmp     loc_18001D889
0x18001d719  test    sil, sil
0x18001d71c  jz      short loc_18001D753
0x18001d71e  mov     rcx, [rbx+10h]; union _LARGE_INTEGER
0x18001d722  mov     edx, 10E0h; unsigned int
0x18001d727  call    ?CompareTimeThreshold@@YAJT_LARGE_INTEGER@@K@Z; CompareTimeThreshold(_LARGE_INTEGER,ulong)
0x18001d72c  cmp     eax, 0FFFFFFFFh
0x18001d72f  jnz     short loc_18001D753
0x18001d731  lea     rdx, [rbp+arg_0]
0x18001d735  mov     [rbp+arg_0], 25h ; '%'
0x18001d73c  mov     rcx, rdi
0x18001d73f  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d744  inc     qword ptr [rax]
0x18001d747  mov     [rbp+arg_0], 26h ; '&'
0x18001d74e  jmp     loc_18001D889
0x18001d753  mov     rcx, [rbx+10h]; union _LARGE_INTEGER
0x18001d757  mov     edx, 870h; unsigned int
0x18001d75c  call    ?CompareTimeThreshold@@YAJT_LARGE_INTEGER@@K@Z; CompareTimeThreshold(_LARGE_INTEGER,ulong)
0x18001d761  cmp     eax, 0FFFFFFFFh
0x18001d764  jnz     short loc_18001D7A8
0x18001d766  lea     rdx, [rbp+arg_0]
0x18001d76a  mov     rcx, rdi
0x18001d76d  test    sil, sil
0x18001d770  jz      short loc_18001D78D
0x18001d772  mov     [rbp+arg_0], 23h ; '#'
0x18001d779  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d77e  inc     qword ptr [rax]
0x18001d781  mov     [rbp+arg_0], 24h ; '$'
0x18001d788  jmp     loc_18001D889
0x18001d78d  mov     [rbp+arg_0], 21h ; '!'
0x18001d794  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d799  inc     qword ptr [rax]
0x18001d79c  mov     [rbp+arg_0], 22h ; '"'
0x18001d7a3  jmp     loc_18001D889
0x18001d7a8  mov     rcx, [rbx+10h]; union _LARGE_INTEGER
0x18001d7ac  mov     edx, 5A0h; unsigned int
0x18001d7b1  call    ?CompareTimeThreshold@@YAJT_LARGE_INTEGER@@K@Z; CompareTimeThreshold(_LARGE_INTEGER,ulong)
0x18001d7b6  cmp     eax, 0FFFFFFFFh
0x18001d7b9  jnz     short loc_18001D7DD
0x18001d7bb  lea     rdx, [rbp+arg_0]
0x18001d7bf  mov     [rbp+arg_0], 1Fh
0x18001d7c6  mov     rcx, rdi
0x18001d7c9  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d7ce  inc     qword ptr [rax]
0x18001d7d1  mov     [rbp+arg_0], 20h ; ' '
0x18001d7d8  jmp     loc_18001D889
0x18001d7dd  mov     rcx, [rbx+10h]; union _LARGE_INTEGER
0x18001d7e1  mov     edx, 2D0h; unsigned int
0x18001d7e6  call    ?CompareTimeThreshold@@YAJT_LARGE_INTEGER@@K@Z; CompareTimeThreshold(_LARGE_INTEGER,ulong)
0x18001d7eb  cmp     eax, 0FFFFFFFFh
0x18001d7ee  jnz     short loc_18001D80F
0x18001d7f0  lea     rdx, [rbp+arg_0]
0x18001d7f4  mov     [rbp+arg_0], 1Dh
0x18001d7fb  mov     rcx, rdi
0x18001d7fe  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d803  inc     qword ptr [rax]
0x18001d806  mov     [rbp+arg_0], 1Eh
0x18001d80d  jmp     short loc_18001D889
0x18001d80f  mov     rcx, [rbx+10h]; union _LARGE_INTEGER
0x18001d813  mov     edx, 150h; unsigned int
0x18001d818  call    ?CompareTimeThreshold@@YAJT_LARGE_INTEGER@@K@Z; CompareTimeThreshold(_LARGE_INTEGER,ulong)
0x18001d81d  cmp     eax, 0FFFFFFFFh
0x18001d820  jnz     short loc_18001D841
0x18001d822  lea     rdx, [rbp+arg_0]
0x18001d826  mov     [rbp+arg_0], 1Bh
0x18001d82d  mov     rcx, rdi
0x18001d830  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d835  inc     qword ptr [rax]
0x18001d838  mov     [rbp+arg_0], 1Ch
0x18001d83f  jmp     short loc_18001D889
0x18001d841  mov     rcx, [rbx+10h]; union _LARGE_INTEGER
0x18001d845  mov     edx, 0A8h; unsigned int
0x18001d84a  call    ?CompareTimeThreshold@@YAJT_LARGE_INTEGER@@K@Z; CompareTimeThreshold(_LARGE_INTEGER,ulong)
0x18001d84f  lea     rdx, [rbp+arg_0]
0x18001d853  mov     rcx, rdi
0x18001d856  cmp     eax, 0FFFFFFFFh
0x18001d859  jnz     short loc_18001D873
0x18001d85b  mov     [rbp+arg_0], 19h
0x18001d862  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d867  inc     qword ptr [rax]
0x18001d86a  mov     [rbp+arg_0], 1Ah
0x18001d871  jmp     short loc_18001D889
0x18001d873  mov     [rbp+arg_0], 17h
0x18001d87a  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d87f  inc     qword ptr [rax]
0x18001d882  mov     [rbp+arg_0], 18h
0x18001d889  mov     rbx, [rbx+28h]
0x18001d88d  lea     rdx, [rbp+arg_0]
0x18001d891  mov     rcx, rdi
0x18001d894  call    ??A?$map@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@@std@@QEAAAEA_K$$QEAK@Z; std::map<ulong,unsigned __int64>::operator[](ulong &&)
0x18001d899  add     [rax], rbx
0x18001d89c  add     rsp, 28h
0x18001d8a0  pop     rdi
0x18001d8a1  pop     rsi
0x18001d8a2  pop     rbx
0x18001d8a3  pop     rbp
0x18001d8a4  retn
```
